pipeline {
  agent any
  stages {
    stage('Cloning GitHub repo') {
      steps {
        echo 'Clonando repositório…'
        checkout([
          $class: 'GitSCM',
          branches: [[name: '*/main']],
          extensions: [],
          userRemoteConfigs: [[
            url:           'https://github.com/EduardoSantosSousa/MLOPS-COURSE-PROJECT-1.git',
            credentialsId: 'github-token'
          ]]
        ])
      }
    }
  }
}
