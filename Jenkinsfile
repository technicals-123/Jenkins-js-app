def gv
pipeline {
    agent any
   environment{
     SERVER_CREDENTIALS=credentials('server-credentials')
   }
// tools{
//     maven 'Maven'
// }
   parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }

    stages {
        stage("init"){
            script{
                 gv=load "script.groovy"
            }
        }
        stage("build") {
            steps {
              script{
                gv.buildApp()
              }
               // echo 'building the application'
               // // sh "mvn install"
            }
        }
        stage("test") {
             steps {
              script{
                gv.testApp()
              }
               // echo 'testing the application'
            }
            
        }
        stage("deploy") {
            steps {
              script{
                 gv.deployApp()
              }
               // echo 'deploying the application'
               // echo"credentials req to open ${SERVER_CREDENTIALS}"
               // sh "${SERVER_CREDENTIALS}"
            }
        }
    }        
}
       
      
