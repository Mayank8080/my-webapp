pipeline {
    agent any
    stages{
        stage("git"){
            steps{
                git 'https://github.com/Mayank8080/my-webapp.git'
            }
        }
        stage("Build"){
            steps{
                sh 'mvn clean install'
            }
        }
    }

