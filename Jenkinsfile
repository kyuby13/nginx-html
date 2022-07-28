env.DOCKER_REGISTRY = 'yubyanime'
env.DOCKER_IMAGE_NAME = 'testing'
pipeline {
    agent any
    stages {
        stage('Git Pull from Github') {
            steps {
                git credentialsId: 'GitHub', url: 'https://github.com/kyuby13/nginx-html.git'
            }
        }    
        stage('Build Docker Image') {
            steps {
                echo "welcome to jenkins"
            }
        }                 
    }
}
