pipeline {
    agent any
    
    parameters {
	    choice(
            name: 'VERSION', 
            choices: ['v1.1' , 'v1.2', 'v1.3'],
            description: 'Build Version'
            )
    }

    environment {
        MESSAGE = 'WELCOME TO JENKINS BUILD'
        CREDENTIALS_GIT = credentials('git_token_credentials')
    }

    stages {
        stage('Build') {
            steps {
                echo "${MESSAGE}"
                echo "Cloning Python repository from Problem branch"
                git credentialsId: 'git_token_credentials', url: 'https://github.com/Bonny10/Python.git', branch: 'Problem'
                sh '''
                    cd Python
                    python --version
                    python Hello_world.py
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing jenkins build version ${VERSION}'
            }
        }
        stage('Deploy') {
            steps {
                echo 'You are in deploy stage...'
            }
        }
    }
    post{
        always {
            echo 'You have successfully run a build in jenkins'
        }
        success {
            echo 'Your build is successfull congratulations'
        }
        failure {
            echo 'Sorry for fail build'
        }
    }
}
