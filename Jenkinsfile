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
                    sh 'docker build -t slashlinux/nodeapp_test:latest .'
                }
            }
        }
        stage('Login to DockerHub'){
            steps{
                script{
                   sh 'docker login -u slashlinux -p AMpt157B@'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   sh 'docker push slashlinux/nodeapp_test:latest'
                }
            }
        }

    }
}
