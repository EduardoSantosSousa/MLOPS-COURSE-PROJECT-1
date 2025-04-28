pipeline {
  agent any

  environment{
    VENV_DIR = 'venv'
    GCP_PROJECT = "serious-cat-455501-d2"
    GCLOUD_PATH = "/var/jenkins_home/google-cloud-sdk/bin"
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
    stage('Building and Pushing Docker Image to GCR') {
      steps {
        withCredentials([file(credentialsId : 'gcp-key', variable : 'GOOGLE_APPLICATION_CREDENTIALS' )]){
          script{
              echo'Building and Pushing Docker Image to GCR................................'
              sh'''
              export PATH=$PATH:${GCLOUD_PATH}

              gcloud auth activate-service-account --key-file=${GOOGLE_APPLICATION_CREDENTIALS}

              gcloud config set project ${GCP_PROJECT}

              gcloud auth configure-docker --quiet

              docker build -t gcr.io/${GCP_PROJECT}/ml-project:latest .

              docker push gcr.io/${GCP_PROJECT}/ml-project:latest
              '''
          }
        }
      }
    }

    stage('Deploy to Google Cloud Run') {
      steps {
        withCredentials([file(credentialsId : 'gcp-key', variable : 'GOOGLE_APPLICATION_CREDENTIALS' )]){
          script{
              echo'Deploy to Google Cloud Run................................'
              sh'''
              export PATH=$PATH:${GCLOUD_PATH}

              gcloud auth activate-service-account --key-file=${GOOGLE_APPLICATION_CREDENTIALS}

              gcloud config set project ${GCP_PROJECT}

              gcloud run deploy ml-project \
                --image=gcr.io/${GCP_PROJECT}/ml-project:latest \
                --platform=managed \
                --region=us-central-1 \
                --allow=unauthenticated


              '''
          }
        }
      }
    }




  }
}
