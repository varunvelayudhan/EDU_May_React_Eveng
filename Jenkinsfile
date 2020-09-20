pipeline {
    agent none 
     environment {
            CI = 'true'
        }
    stages {
        stage('Build') {
            agent {
                docker "build-tools-image"
            }
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            agent {
                docker "build-tools-image"
            }
                    steps {
                        sh './jenkins/scripts/test.sh'
                    }
                }
                stage('Deliver') {
                    agent {
                docker "build-tools-image"
            }
                            steps {
                                sh './jenkins/scripts/deliver.sh'
                                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                                sh './jenkins/scripts/kill.sh'
                            }
                        }

    }
}
