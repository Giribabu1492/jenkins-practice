pipeline {
    agent { label 'AGENT-1' }

    environment {
    PROJECT = "EXPENSE"
    COMPONENT= "BACKEND"
    }

    options {
        disableConcurrentBuilds()
        timeout(time: 30, unit: 'MINUTES')
    }

    parameters {
        string(name: 'PROJECT', defaultValue: 'EXPENSE', description: 'Project name')
        string(name: 'COMPONENT', defaultValue: 'BACKEND', description: 'Component name')
    }







    stages {
        stage('Build') {
            steps {
                script {
                    sh '''
                        echo "Hello world"
                        echo "project name is $PROJECT"
                        echo "component name is $COMPONENT"
                        

                        
                    '''
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh '''
                        echo "hello this is test"
                        echo "This is Project related information: ${params.PROJECT}"
                        echo "This is Component related information: ${params.COMPONENT}"
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
