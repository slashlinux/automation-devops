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
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'AMpt157B@', variable: 'dockerhubpwd')]) {
                   sh 'docker login -u slashlinux -p ${dockerhubpwd}'

}
                   sh 'docker push slashlinux/nodeapp_test:latest'
                }
            }
        }

    }
}
