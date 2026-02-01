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
                    npm ci
                    npm run build
                    ls -la
                    node_modules/.bin/serve -s build &
                '''
            }
        }
    }
}

