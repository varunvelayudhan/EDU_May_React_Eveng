pipeline {
    agent none 
     environment {
            CI = 'true'
        }
    stages {
        stage('Build') {
            agent none
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            agent none
                    
                }
                stage('Deliver') {
                    agent none
                            steps {
                                sh './jenkins/scripts/deliver.sh'
                                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                                sh './jenkins/scripts/kill.sh'
                            }
                        }

    }
}
