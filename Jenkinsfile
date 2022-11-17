pipeline {
    agent any
    stages {

        stage('deploy to remote dev server') {
            when {
                branch 'Dev-1'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa  /var/lib/jenkins/workspace/brij_multi_Dev-1/* ubuntu@65.2.146.212:/home/ubuntu/dev/ "
            }
        }

        stage('deploy to remote main branch ') {
            when {
                branch 'main'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa  /var/lib/jenkins/workspace/brij_multi_main/* ubuntu@65.2.146.212:/home/ubuntu/main/ "
            }
        }
    }   
}
 
  
