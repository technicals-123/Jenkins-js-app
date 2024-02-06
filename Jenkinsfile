pipeline {
    agent any
   environment{
     SERVER_CREDENTIALS=credentials('server-credentials')
   }
tools{
    maven 'Maven'
}
    stages {
        stage("build") {
            steps {
               echo 'building the application'
               sh "mvn install"
            }
        }
        stage("test") {
             steps {
               echo 'testing the application'
            }
            
        }
        stage("deploy") {
            steps {
               echo 'deploying the application'
               echo"credentials req to open ${SERVER_CREDENTIALS}"
               // sh "${SERVER_CREDENTIALS}"
            }
        }
    }        
}
       
      
