pipeline {
    agent any
    tools{
        maven "3.6.3"
    }
    stages {
        stage('Build stage') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test stage') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy stage') {
            steps{
            script {
        deploy adapters: [tomcat9(credentialsId: 'admin', url: 'http://3.25.220.79:8080/')], contextPath: '', onFailure: false, war: 'target/*.war' 
}
                }
        }
    }
}
