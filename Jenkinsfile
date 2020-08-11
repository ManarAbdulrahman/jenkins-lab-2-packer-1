pipeline {

    agent {
        docker {
            image 'bryandollery/alpine-docker'
            args "-u root"
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
                sh "make build"
                
            }
        }
       
        
    }
} 
