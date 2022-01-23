pipeline {
    agent any 
    stages {
        stage('prep') { 
            steps {
             git url: 'https://github.com/Shfarrukhb/weekly-team-report-html.git', branch:'develop-team-1'
             sh "apt install npm -y"
             sh "npm install"
             sh "npm run build"
                // 
            }
        }
        stage('terraform install and build') { 
            steps {
              sh "terraform init"
              sh "terraform plan"
              sh "terraform apply --auto-approve"
                //
            }
        }
         stage('uploading static site content') {
             steps {
              sh "curl https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip -o awscliv2.zip"
              sh "unzip awscliv2.zip"
              sh "sudo ./aws/install" 
                 //
             }
          }
       }
    }
