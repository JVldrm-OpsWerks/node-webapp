pipeline {
    agent {
      label 'linux-node'
}
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: 'JVldrm-OpsWerks', url: 'https://github.com/JVldrm-OpsWerks/node-webapp.git'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('node-webapp:latest')
                }
            }
        }
        
        stage('Run Docker Image') {
            steps {
                script {
                    docker.image('node-webapp:latest').run('-d -p 3000:3000') {
                       
                    }
                }
            }
        }
    }
}
