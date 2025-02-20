pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/Abhishekbleh8899/docker_jenkins.git',
                    credentialsId: 'your-git-credentials-id'
            }
        }

        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh ''' 
                node --version
                npm --version
                npm install
                npm run build
                '''
            }
        }
    }
}
