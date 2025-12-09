pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull from main branch explicitly
                git branch: 'main',
                    url: 'https://github.com/Mariam2026/cloudtask.git'
            }
        }

        stage('Build') {
            steps {
                // Compile Java project using Maven
                sh 'mvn clean compile'
            }
        }

        stage('Run Tests') {
            steps {
                // Run JUnit tests
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            // Collect JUnit test reports
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
