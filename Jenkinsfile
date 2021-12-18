pipeline {
    agent any
    tools {
        maven 'MVN'
    }
    stages {
        stage('01 - Git Checkout'){
            steps {
                git 'https://github.com/PMVVSV/warapplication.git'
            }
        }
        stage('02 - Test') {
            steps {
                sh 'mvn clean test'
            }
        }
        stage('03 - Package') {
            steps {
                sh 'mvn clean package'
            }
        }
         stage('04 - Deploy') {
             steps{
           deploy adapters: [tomcat9(credentialsId: '5ca39a88-cd22-4dc5-92fe-19826bbcd480', path: '', url: 'http://20.119.42.134:8081/')], contextPath: 'boxfuse-sample-java-war-hello', war: '**/*.war'
            }
         }
    }
}
