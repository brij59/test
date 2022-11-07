pipeline {
    agent any
    stages {

        stage('deploy to remote dev server') {
            when {
                branch 'Dev-1'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa  /var/lib/jenkins/workspace/multi branch-brij_Dev-1/* ubuntu@65.2.122.90:/home/ubuntu/dev/ "
            }
        }

        stage('deploy to remote main branch ') {
            when {
                branch 'main'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/.ssh/id_rsa  /var/lib/jenkins/workspace/multi branch-brij_main/* ubuntu@65.2.122.90:/home/ubuntu/main/ "
            }
        }
    }   
}
