pipeline {
    agent any
    
    tools {nodejs "node"}
    
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh "chmod +x -R ./scripts/test.sh"
                sh './scripts/test.sh'
            }
        }
         stage('Deliver') {
                            steps {
                                sh "chmod +x ./scripts/deliver.sh"
                                sh './scripts/deliver.sh'
                                input message: 'Hello world'
                                sh "chmod +x ./scripts/kill.sh"
                                sh './scripts/kill.sh'
                            }
                        }
            }
      }