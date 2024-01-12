pipeline {
    agent any
    stages{
        stage('gitclone'){
            steps{
                git 'https://github.com/shazforiot/nodeapp_test.git'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t 28041986/nodeapp_test:latest .'
                }
            }
        }
        stage('Login to DockerHub'){
            steps{
                script{
                   sh 'docker login -u 28041986 -p AMpt157B...'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   sh 'docker push 28041986/nodeapp_test:latest'
                }
            }
        }

    }
}
