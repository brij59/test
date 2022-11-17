pipeline {
    agent any
    stages {

        stage('deploy to remote dev server') {
            when {
                branch 'Dev-1'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/brijraj.pem /var/lib/jenkins/workspace/brij_multi_Dev-1/* ubuntu@13.232.149.127:/home/ubuntu/dev1/ "
            }
        }

        stage('deploy to remote main branch ') {
            when {
                branch 'main'
            }
            steps {
                sh  "scp -r -i   /var/lib/jenkins/brijraj.pem  /var/lib/jenkins/workspace/brij_multi_main/* ubuntu@13.232.149.127:/home/ubuntu/main1/ "
            }
        }
    }   
}
 
