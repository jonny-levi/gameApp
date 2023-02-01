pipeline {
    agent {
        label {
            label 'mater_node01'
        }
    }
    stages{
        stage('Fetch'){
            steps{
              sh '''
                    rm -rf k8s 
                    git clone https://github.com/jonny-levi/k8s.git
                '''
            }
        }
        
        stage('Build'){
            steps{
                sh ''' 
                       kubectl delete -f k8s/app1/guess_my_number_deploy.yaml
                       kubectl delete -f k8s/app1/guess_my_number_service.yaml
                       kubectl create -f k8s/app1/guess_my_number_deploy.yaml
                       kubectl create -f k8s/app1/guess_my_number_service.yaml
                        '''
            }
        }
        
    }
}