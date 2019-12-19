pipeline {
    agent {
        label 'linux'
    }
    options {
        buildDiscarder (logRotator(daysToKeepStr: '100', numToKeepStr: '100'))
    }
    
    stages {
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
                emailext body: 'SUCCESS', to: 'gsridharmsc@gmail.com'
            }
            failure {
                emailext body: 'FAILURE', to: 'gsridharmsc@gmail.com'
            }
            
        }
    
}
