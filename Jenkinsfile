pipeline {

    agent any

    stages {

        stage("build") {

            steps{
                echo 'Validating infrastructure code'
                sh 'openstack orchestration template validate -f main_template.yaml'
                
              
            }
        }

        stage("test") {

            steps{
                echo 'Running infrastructure test...'
                sh 'pytest main_infrastructure.py'
               
            }
        }

        stage("deploy") {

            steps{
                echo 'Deploying infrastructure...'
                sh 'openstack stack create -t main_template.yaml my_stack'
                
            }
        }

    }

}
