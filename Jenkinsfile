pipeline {
    agent {
        
        label 'docker'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    
                    sh 'docker build -t tahany/docker-react -f Dockerfile.dev .'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    env.DOCKER_BUILDKIT = 1  
                    sh 'docker run -e CI=true tahany/docker-react npm run test'
                }
            }
        }
    }
}

// this file  is for testing the webhookkk