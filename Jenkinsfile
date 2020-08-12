pipeline {

    agent {
        docker {
            image 'bryandollery/terraform-packer-aws-alpine'
            args "-u root --entrypoint='' "
        }
    }
     environment {
        CREDS = credentials('6c22797b-6e23-4779-984c-c18d46aade6b')
        WONER = "MANAR"
        AWS_ACCESS_KEY_ID= "${CREDS_USR}"
        AWS_SECRET_ACCESS_KEY= "${CREDS_PSW}"
    }
    stages {
       
     stage ('build') {
         
            steps {
                sh "Make init"
                sh "make start"
                sh "packer build packer.json "
                
            }
        }
        post {
            success {
                build job: "Manar-webserver", wait: false
            //add a commment
            }
        }
        
    }
} 
