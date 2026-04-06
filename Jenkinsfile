pipeline {
    agent {label 'AGENT-1'}
    environment {
        // Define environment variables here
        // For example: MY_VAR = "value"
        project_name = "Expense Tracker"
        component = "Backend"
        Deployment_Env = "qa"
    }
    options {
        // Define pipeline options here
        // For example: timeout(time: 1, unit: 'HOURS')

        disableConcurrentBuilds() // Prevent concurrent builds of this pipeline
        timeout(time: 30, unit: 'MINUTES') // Set a timeout for the entire pipeline
    }
    // parameters {
    //     // Define parameters 

    //      string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

    //     text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

    //     booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

    //     choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

    //     password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
        
    //     }

    
    stages {
        stage('Build') {
            steps {
              script{
                sh """

                echo "hello, this is build"
                echo "project_name: ${project_name}"
                echo "component: ${component}"
          
                # echo "Hello ${params.PERSON}"

                # echo "Biography: ${params.BIOGRAPHY}"

                # echo "Toggle: ${params.TOGGLE}"

                # echo "Choice: ${params.CHOICE}"

                # echo "Password: ${params.PASSWORD}"
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
          // input {
          //       message "Should we continue?"
          //       ok "Yes, we should."
          //       submitter "alice,bob"
          //       parameters {
          //           string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
          //       }
          //}
          when {
              // environment name: 'Deployment_Env', value: 'production'
              environment name: 'Deployment_Env', value: 'qa'
              }
            steps {
                 script{
                sh """
                echo "hello, this is deployment"
              
                """
              }
                
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

