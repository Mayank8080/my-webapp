pipeline {
    agent any

    stages{
        stage("git"){
            steps{
                git url: 'https://github.com/Mayank8080/my-webapp.git', branch: 'main'

            }
        }
        stage("Build"){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat(credentialsId: 'TomcatCredentials', url: 'http://localhost:9090')],  contextPath: '/webapp', war: '**/*.war'
            }
        }
        }
}

