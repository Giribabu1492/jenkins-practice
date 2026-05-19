pipeline {
    agent { label 'AGENT-1' }

    environment {
        PROJECT = "EXPENSE"
        COMPONENT = "BACKEND"
    }

    options {
        disableConcurrentBuilds()
        timeout(time: 30, unit: 'MINUTES')
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'EXPENSE', description: 'Project name')
        string(name: 'BIOGRAPHY', defaultValue: 'BACKEND', description: 'Component name')
        string(name: 'mobile', defaultValue: 'BACKEND', description: 'Component name')
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                    echo "Hello world"
                    echo "project name is $PROJECT"
                    echo "component name is $COMPONENT"
                '''
            }
        }

        stage('Test') {
            steps {
                sh """
                    echo "hello this is test"
                    echo "This is Project related information: ${params.PERSON}"
                    echo "This is Component related information: ${params.BIOGRAPHY}"
                """
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    echo "hello this is deploy"
                '''
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