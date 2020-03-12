pipeline {
  agent any
  stages {
    stage('code-pull') {
      steps {
        git(url: 'https://github.com/innomatics321/Narendraapplication.git', branch: 'master', credentialsId: 'narendrasingamaneni91')
      }
    }

    stage('compile') {
      parallel {
        stage('compile') {
          steps {
            bat 'mvn compile'
          }
        }

        stage('test') {
          steps {
            bat 'mvn test'
          }
        }

      }
    }

    stage('build') {
      steps {
        bat 'mvn package'
      }
    }

  }
}