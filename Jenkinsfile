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
                deploy adapters: [tomcat9(credentialsId: '04fc1744-99ea-453d-b82e-2f8bc13c9fb8', url: 'http://localhost:9006/manager/html')], contextPath: null, war: 'target/*.war'
            }
        }
        }
}

