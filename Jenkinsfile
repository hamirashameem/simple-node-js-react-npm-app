pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
            sh 'npm install'
            }
        }
        stage('Test'){
            steps{
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver'){
            steps{
                sh './jenkins/scripts/deliver.sh'
                input message: " Finished using the web site? (Clikc "proceed" to contine)"
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}