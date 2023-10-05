pipeline{
    agent { node { label 'terra' } }

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
        stage('validation') {
            steps {
                input('do yoy still wanted to proceed')
            }
        }
            
        stage('apply') {
            steps {
                sh '''
                terraform apply --auto-approve
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