//


pipeline {

    agent any

    // Defines the stages of the pipeline.
    stages {

        //Stage to validate infrastructure code
        stage("build") {
            steps{
                echo 'Validating infrastructure code'

                // Run the heat template validation command to check the syntax
                sh 'heat template-validate -f main_infrastructure.yaml'
              
            }
        }

        //Stage 2 run infrastructure tests
        stage("test") {
            steps{
                echo 'Running infrastructure test'
               
            }
        }
        
        // Stage 3: Deploy Infrastructure
        stage("deploy") {

            steps{
                echo 'Deploying infrastructure'
                
            }
        }

    }

}
