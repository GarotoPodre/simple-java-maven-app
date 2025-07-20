pipeline {
    agent any
    tools {
        maven 'apache-maven' // Ex: 'apache-maven-3.9.6'
        jdk 'jdk-17'    // Ex: 'jdk-17'
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
     stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
}