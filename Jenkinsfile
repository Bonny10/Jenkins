pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'You are in Build stage...'
            }
        }
        stage('Test'){
            steps{
                echo 'You are in test stage...'
            }
        }
        stage('Deploy'){
            steps{
                echo 'You are in deploy stage...'
            }
        }
    }
    post{
        always{
            echo 'You have successfully run a build in jenkins'
        }
        success{
            echo 'Your build is successfull congratulations'
        }
        failure{
            echo 'Sorry for fail build'
        }
    }
}

