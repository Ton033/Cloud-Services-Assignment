pipeline {

    agent any

    stages {

        stage("build") {

            steps{
                echo 'Validating infrastructure code'
                sh 'heat template-validate -f main_infrastructure.yaml'
              
            }
        }

        stage("test") {

            steps{
                echo 'Running infrastructure test'
               
            }
        }

        stage("deploy") {

            steps{
                echo 'Deploying infrastructure'
                
            }
        }

    }

}
