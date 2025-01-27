pipeline {

    agent any

    environment {
        BRANCH_NAME = 'main'
        GIT_URL = 'https://github.com/Le-Moktar/wweek6-Git-bash-shell-script.git'
    }

    stages {

        stage ('Github checkout'){
            steps{
                git branch: "${BRANCH_NAME}", url: "${GIT_URL}"
            }
        }
       stage ('Init'){
            steps{
                sh 'terraform init -migrate-state -no-color'
                sh 'terraform init --upgrade -no-color'
            }
        }
        stage ('validate'){
            steps{
                sh 'terraform validate -no-color'
            }
        }
        stage ('plan'){
            steps{
                sh 'terraform plan -no-color'
            }
        }
         stage ('apply'){
            steps{
                sh 'terraform apply --auto-approve -no-color'
            }
        }
    }
}