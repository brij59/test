pipeline {
    agent any
    stages {
        
         stage('Deployment step') {

            steps {
                timeout(time: 15, unit: "MINUTES") {
                    input message: 'Do you want to approve the deployment?', ok: 'Yes'
                }

                echo "Initiating deployment"
            }
        }

        stage('deploy to remote dev server') {
            when {
                branch 'Dev-1'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa /var/lib/jenkins/workspace/brij_multi_Dev-1/* ubuntu@13.232.149.127:/home/ubuntu/dev1/ "
            }
        }

        stage('deploy to remote main branch ') {
            when {
                branch 'main'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa  /var/lib/jenkins/workspace/brij_multi_main/* ubuntu@13.232.149.127:/home/ubuntu/main1/ "
            }
        }
    }   
}
 
