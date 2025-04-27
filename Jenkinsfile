pipeline {
  agent any

  environment{
    VENV_DIR = 'venv'
  }

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
    stage('Setting up our Virtual Environment and Installing Dependancies') {
      steps {
        echo 'Setting up our Virtual Environment and Installing Dependancies.........'
        sh '''
        python -m venv ${VENV_DIR}
        . ${VENV_DIR}/bin/activate
        pip install --upgrade pip
        pip install -e .

        '''
      }
    }




  }
}
