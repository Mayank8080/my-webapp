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
                deploy adapters: [tomcat9(credentialsId: 'TomcatCredentials', path: '/webapp', url: 'http://localhost:9090')], contextPath: /webapp, war: '**/*.war'
            }
        }
        }
}

