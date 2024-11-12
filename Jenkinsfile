pipeline {

    agent any

    stages {

        stage("build") {

            steps{
                echo 'Validating infrastructure code'
                sh 'yamllint main_infrastructure.yaml' 
                sh 'heat-template-validate -f main_infrastructure.yaml'
              
            }
        }

        stage("test") {

            steps{
                echo 'Running infrastructure test...'
                sh 'inspec exec tests/'
               
            }
        }

        stage("deploy") {

            steps{
                echo 'Deploying infrastructure...'
                sh 'openstack stack create -t main_infrastructure.yaml --parameter ...'
                
            }
        }

    }

    post {
        always {
            echo 'Cleaning up resources...'
            // Optional cleanup step if infrastructure is temporary
            sh 'openstack stack delete your-stack-name --yes'
        }
    }
}
