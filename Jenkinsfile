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
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa  /var/lib/jenkins/workspace/multi branch-brij
_Dev-1/* ubuntu@65.2.122.90:/home/ubuntu/dev/ "
            }
        }

        stage('deploy to remote main branch ') {
            when {
                branch 'main'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa  /var/lib/jenkins/workspace/multi branch-brij
_main/* ubuntu@65.2.122.90:/home/ubuntu/main/ "
            }
        }
    }   
}
