env.DOCKER_REGISTRY = 'yubyanime'
env.DOCKER_IMAGE_NAME = 'testing'
pipeline {
    agent any
    stage('login server') {         
            steps{
              sh "ssh root@54.151.178.26"        
            }
        }
    stages {
        stage('Bikin Folder') {
            steps {
                sh "mkdir /home/test"
            }
        }    
      
    }
}

