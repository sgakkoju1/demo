 @Library('pipeline-library-demo')_

pipeline {
    agent any
 
    options {
        buildDiscarder (logRotator(daysToKeepStr: '100', numToKeepStr: '100'))
    }
    
    stages {
        
        stage('DemoFromLibrary') {
         steps {
          script {
            echo 'Using Shared Libraries using Jenkins'
           echo 'call function number : 1'
            sayHello 'Dave'
           
           echo 'call function number : 2'
           sayHello 'Sridhar'
           
           echo 'call function number : 3'
           sayHello 'Gakkoju'
           
           echo 'call function number with no passing parameter: 4'
           sayHello 
           
           echo 'call function number with null passing null value: 5'
           sayHello ''
           
           
          }
         }
        }        
     
     devPipeline
        
//        stage('Build') {
//            steps {
//                script {
//                echo "Build Stage"
//                }
//            }
//        }
        
//        stage('Test') {
//            steps {
//                script {
//                echo "Test Stage"
//                }
//            }
//        }
    }
        post{
            always {
                deleteDir()
            }
            success {
                emailext body: 'SUCCESS', subject: '$BUILD_NUMBER - SUCCESS', to: 'gsridharmsc@gmail.com'
            }
            failure {
                emailext body: 'FAILURE', subject: '$BUILD_NUMBER - FAILURE', to: 'gsridharmsc@gmail.com'
            }
            
        }
    
}
