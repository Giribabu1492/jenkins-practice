pipeline {
    agent { label 'AGENT-1' }
    environment {
    PROJECT = "EXPENSE"
    COMPONENT= "BACKEND"
    }
    options {
        disableConcurrentBuilds()
    }





    stages {
        stage('Build') {
            steps {
                script {
                    sh '''
                        echo "Hello world"
                        echo "project name is $PROJECT"
                        echo "component name is $COMPONENT"
                        sleep 15
                    '''
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh '''
                        echo "hello this is test"
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh '''
                        echo "hello this is deploy"
                    '''
                }
            }
        }
    }

    post {
        always {
            echo "This will always run"
        }
        failure {
            echo "This will run only if the pipeline fails"
        }
        success {
            echo "Pipeline completed successfully!"
        }
    }
}
