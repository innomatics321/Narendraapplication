pipeline {
  agent any
  stages {
    stage('code-pull') {
      steps {
        git(url: 'https://github.com/innomatics321/Narendraapplication.git', branch: 'master', credentialsId: 'narendrasingamaneni91')
      }
    }

    stage('install') {
      steps {
        bat 'mvn clean install'
      }
    }

    stage('deploy') {
      steps {
        bat 'xcopy "C:\\Program Files (x86)\\Jenkins\\workspace\\intex_master\\target" "C:\\Program Files\\Apache Software Foundation\\Tomcat 8.5\\webapps"'
      }
    }

  }
}