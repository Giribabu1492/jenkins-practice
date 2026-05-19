pipeline {
    agent {label 'AGENT-1'}

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

        stage('Parallel Stage') {
            parallel {
                stage('Parallel Stage - 1') {
                    steps {
                        script {
                            sh '''
                                echo "this is parallel stage1"
                            '''
                        }
                    }
                }

                stage('Parallel Stage - 2') {
                    steps {
                        script {
                            sh '''
                                echo "this is parallel stage2"
                            '''
                        }
                    }
                }
            }
        }
    }
}
