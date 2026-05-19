pipeline {
    agent { label 'AGENT-1' }

    environment {
        PROJECT = "EXPENSE"
        COMPONENT = "BACKEND"
        DEPLOY_ENV = "QA"
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

            // input {
            //     message "Do you want to proceed with deployment?"
            //     ok "Deploy"
            //     parameters {
            //         string(name: 'DEPLOY_ENV', defaultValue: 'dev', description: 'Environment to deploy to')
            //     }
            // }
            when {

                environment name: 'DEPLOY_ENV', value: 'QA'
            }
            steps {
                sh '''
                    echo "hello this is deploy to successfully"
                    echo "Deploying to environment: $DEPLOY_ENV"
                '''
            }


        }

        stage('parallel stage') {
            parallel {
                stage('parallel stage 1') {
                    steps {
                        sh '''
                            echo "This is parallel stage 1"
                        '''
                    }
                }
                stage('parallel stage 2') {
                    steps {
                        sh '''
                            echo "This is parallel stage 2"
                        '''
                    }
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