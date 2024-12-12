pipeline {
    agent any
    tools {nodejs "NODEJS"}
    stages {
        stage('Build') {
            steps {
                //To run SH command in Windows Jenkins
                //Right click on Computer, click properties > advanced system settings > environmental variables, 
                //add C:\Program Files\Git\bin to your system "Path" property. 
                
                sh 'npm install' 
            }
        }
        stage('Deliver') {
            steps {
                //To run SH command in Windows Jenkins
                //Right click on Computer, click properties > advanced system settings > environmental variables, 
                //add C:\Program Files\Git\bin to your system "Path" property. 

                sh 'chmod -R +rwx ./jenkins/scripts/deliver.sh'
                sh 'chmod -R +rwx ./jenkins/scripts/kill.sh'
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
