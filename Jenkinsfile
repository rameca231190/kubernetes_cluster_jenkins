pipeline{
    agent any
    stages{
        stage("Pull repo"){
            steps{
                git 'https://github.com/rameca231190/created-internal-cluster.git'
                
            }
        }
        stage("Terraform init"){
            steps{
                ws("${workspace}/dev/kubernetes_cluster"){
                    sh "terraform init"
                    
                }
            }
        }
        stage("Terraform Apply"){
            steps{
                ws("${workspace}/dev/kubernetes_cluster"){
                    sh "terraform plan"
                }
            }
        }
    }
}
