pipeline {
    agent {
        label {
            label 'mater_node01'
        }
    }
    stages{
        stage('Fetch'){
            steps{
              sh ''' git clone https://github.com/jonny-levi/k8s.git
                    cd k8s
                '''
            }
        }
        
        stage('Build'){
            steps{
                sh ''' kubectl create -f guess_my_number_deploy.yaml
                       kubectl create -f guess_my_number_service.yaml '''
            }
        }
        
    }
}