pipeline{

    agent {label 'AGENT-1'}


    stages{


        stage('Build')

            steps{
                script{

                        """
                        echo "Hello world"
                        """
                }



            }

        stage('Test') {

            steps{
                script{
                    """
                    echo "hello this is test"
                    """
                }


            }


        }    

        stage ('parallel stage'){

            parallel{
             stage('parallel stage -1'){
                steps {
                    script{

                        """
                        echo "this is parallel stage1"
                    }

                }
                 stage ('parallel stage -2'){

                    steps {

                        script
                    }
                 }


             }
            }

        }





    }
























}