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

        stage('install') {
          steps {
            bat 'mvn clean install'
          }
        }

      }
    }

    stage('build') {
      steps {
        bat 'mvn package'
      }
    }

    stage('deploy') {
      steps {
        bat 'xcopy"C:\\Program Files (x86)\\Jenkins\\workspace\\intex_master\\target\\intex.war" "c:\\program files\\apache software foundation\\tomcat8.5\\webapps"/y'
      }
    }

  }
}