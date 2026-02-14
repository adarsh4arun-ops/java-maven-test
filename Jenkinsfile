pipeline {
    agent any

    tools {
        maven "Default"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/adarsh4arun-ops/java-maven-test.git'
            }
        }

        stage('Build & Test') {
            steps {
                bat 'mvn clean package'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
            archiveArtifacts artifacts: 'target/*.jar'
        }
    }
}
