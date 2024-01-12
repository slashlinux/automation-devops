pipeline {
    agent any
    }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t petrisor/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'AMpt157B@', variable: 'dockerhubpwd')]) {
                   sh 'docker login -u slashlinux -p ${dockerhubpwd}'

}
                   sh 'docker push petrisor/devops-integration'
                }
            }
        }
        stage('Deploy to k8s'){
            steps{
                script{
                    kubernetesDeploy (configs: 'deploymentservice.yaml',kubeconfigId: 'k8sconfigpwd')
                }
            }
        }
    }
}
