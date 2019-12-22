// @Library('pipeline-library-demo')_

pipeline {
    agent any
 
    options {
        buildDiscarder (logRotator(daysToKeepStr: '100', numToKeepStr: '100'))
    }
    
    stages {
        
//        stage('DemoFromLibrary') {
//            echo 'Hello world'
//            sayHello 'Dave'
//            }        
        
        stage('Build') {
            steps {
                script {
                echo "Build Stage"
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                echo "Test Stage"
                }
            }
        }
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
