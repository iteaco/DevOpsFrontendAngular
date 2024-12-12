pipeline {
    agent any
    tools {nodejs "NODEJS"}
    stages {
        stage('Build') {
            steps {
                //for Linux
                //sh 'npm install' 

                //for Windows               
                bat 'npm install'
            }
        }
        stage('Deliver') {
            steps {
                //for Linux
                /*
                sh 'chmod -R +rwx ./jenkins/scripts/deliver.sh'
                sh 'chmod -R +rwx ./jenkins/scripts/kill.sh'
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
                */

                //for Windows   
                bat 'chmod -R +rwx ./jenkins/scripts/deliver.sh'
                bat 'chmod -R +rwx ./jenkins/scripts/kill.sh'
                bat '.\jenkins\scripts\deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                bat './jenkins/scripts/kill.sh'
            }
        }
    }
}
