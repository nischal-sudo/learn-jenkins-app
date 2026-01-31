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
                    npm ci
                    npm run build
                    ls -la
                    npm install serve
                    npx serve -s build &
                    //docker run --name nodeapp -p 4000:3000 node:18-alpine
                '''
            }
        }
        // stage('Test'){
        //     // agent{
        //     //     docker{
        //     //         image 'node:18-alpine'
        //     //         reuseNode true
        //     //     }
        //     // }

        //     // // steps{ 
        //     //     sh '''
        //     //         //test -f build/index.html
        //     //         //npm test
        //     //     '''
        //     }
        // }
    }
}

