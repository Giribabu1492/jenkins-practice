pipeline {
    agent {label 'AGENT-1'}
    environment {
        // Define environment variables here
        // For example: MY_VAR = "value"
        project_name = "Expense Tracker"
        component = "Backend"
    }
    options {
        // Define pipeline options here
        // For example: timeout(time: 1, unit: 'HOURS')

        disableConcurrentBuilds() // Prevent concurrent builds of this pipeline
    }

    stages {
        stage('Build') {
            steps {
              script{
                sh """

                echo "hello, this is build"
                echo "project_name: ${project_name}"
                echo "component: ${component}"
                
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

