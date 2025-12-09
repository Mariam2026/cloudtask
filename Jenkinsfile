pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mariam2026/cloudtask.git'
            }
        }

        stage('Build') {
            steps {
                // Full path to Maven
                bat 'C:\\Users\\maria\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn clean compile'
            }
        }

        stage('Run Tests') {
            steps {
                // Full path to Maven
                bat 'C:\\Users\\maria\\Downloads\\apache-maven-3.9.11-bin\\apache-maven-3.9.11\\bin\\mvn test'
            }
        }
    }

    post {
        always {
            // Publish JUnit test results
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
