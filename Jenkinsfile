pipeline {
    agent any
    environment {
        Path = "/usr/share/man/man1/mvn.1.gz:$Path"
    }
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
}
