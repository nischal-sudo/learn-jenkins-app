pipeline{
    agent any
    stages{
        stage('Deploy'){
            steps{
                sh """
                mkdir -p test
                touch test/container.txt
                echo "Hello from Jenkins" >> test/container.txt
                cat test/container.txt
                """
            }
        }
    }
}

