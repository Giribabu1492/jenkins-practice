pipeline {
    agent { label 'AGENT-1' }

    stages {
        stage('Build') {
            steps {
                script {
                    sh '''
                        echo "Hello world"
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
