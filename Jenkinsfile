pipeline {
    agent {label 'AGENT-1'}
    stages {
        stage('Build') {
            steps {
              script{
                sh """
                echo "hello, this is build"
                
                """
              }  //
            }
        }
        stage('Test') {
            steps {
                 script{
                sh """
                echo "hello, this is test"
                
                """
              }
                //
            }
        }
        stage('Deploy') {
            steps {
                 script{
                sh """
                echo "hello, this is deployment"
                aaa
                """
              }
                //
            }
        }
        
    }
    post {
        always {
            echo "This will always run"
        }
        success {
            echo "This will run only if successful"
        }
        failure {
            echo "This will run only if failed"
        }
    }
    
}

