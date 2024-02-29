pipeline {
    agent any
    
    stages {
        stage('Pull from GitHub') {
            steps {
                git 'https://github.com/Hamza-benAmmar/Tp2-Docker-Jenkins-pipeline.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('springboot_mongodb_devopsTP_image')
                }
            }
        }
        
        stage('Push to DockerHub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'hamzabenammar') {
                        docker.image('springboot_mongodb_devopsTP_image').push('latest')
                    }
                }
            }
        }
    }
}
