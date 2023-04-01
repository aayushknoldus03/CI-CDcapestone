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
        deploy adapters: [tomcat9(credentialsId: '1dcfd5ef-4152-40f3-abe1-3992d6db571e', path:'', url: 'http://3.25.220.79:8080/')], contextPath: null, onFailure: false, war: '**/*.war' 
}
                }
        }
    }
}
