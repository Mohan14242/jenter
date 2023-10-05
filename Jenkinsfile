pipeline{
    agent { node { label 'jenter' } }

    stages{
        stage('init') {
            steps {
                sh '''
                terraform init
                '''
            }
        }
       
        stage('plan') {
            steps {
                sh '''
                terraform plan
                '''
            }
        }

        stage ('apply ') {
            steps {
                sh '''
                terraform destroy --auto-approve
                '''
            }
        }

      
    }

    post{
        always {
            echo " i willalways run  wheather job fails or pass i dont matter"
        }
        success{
            echo "i will run onyl when the pipeline is success"
        }
        failure{
            echo " i will run only when the  pipeline fails"
        }
    }
    
}