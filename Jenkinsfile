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
                sh "docker build -t $DOCKER_REGISTRY/$DOCKER_IMAGE_NAME:${BUILD_NUMBER} ."
            }
        }              
        stage('Push Docker Image to Dockerhub') {
            steps {
                sh "docker push $DOCKER_REGISTRY/$DOCKER_IMAGE_NAME:${BUILD_NUMBER}"
            }
        } 
        stage('Remove Docker Image in local') {
            steps {
                sh "docker rmi $DOCKER_REGISTRY/$DOCKER_IMAGE_NAME:${BUILD_NUMBER}"
            }
        }
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }        
    }
}
