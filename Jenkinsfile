pipeline {

    agent {
        docker {
            image 'bryandollery/terraform-packer-aws-alpine'
            args "-u root --entrypoint='' "
        }
    }
     environment {
        CREDS = credentials('8136ddf7-0291-4f78-99b3-15a5cf3d9288')
        WONER = "MANAR"
        AWS_ACCESS_KEY_ID= "${CREDS_USR}"
        AWS_SECRET_ACCESS_KEY= "${CREDS_PSW}"
    }
    stages {
       
     stage ('build') {
         
            steps {
                
                sh "packer build $AWS_ACCESS_KEY_ID  $AWS_SECRET_ACCESS_KEY packer.json "
                
            }
        }
       
        
    }
} 
