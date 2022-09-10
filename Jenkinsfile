pipeline {
    agent any
    parameters {
	string(name: 'Jenkins simple projects', defaultValue:'', description:'')
	booleanParam(name: 'Jenkins_Build', defaultValue: true, description: 'Run this project when true')
	choice(name: 'VERSION', choices: ['v1.0.0' , 'v1.1.0', v1.2.0']
    }
    stages {
        stage('Build') {
            steps {
                echo 'You are in Build stage...'
            }
        }
        stage('Test'){
            when{
                expression{
                    param.Jenkins_Build == true
                }
            }
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

