pipeline{
    agent any
    stages{
        stage('Deploy'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true 
                }
            }
            steps{
                sh '''
                node --version
                npm --version
                rm test
                npm ci
                npm run build
                ls -la
                '''
            }
        }
    }
}

