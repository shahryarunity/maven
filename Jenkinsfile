pipeline {
    agent any

    tools {
        maven 'M3'   // 👈 name you gave in Jenkins tool config
    }

    stages {
        stage('Fetch code') {
            steps {
                git branch: 'main', url: 'https://github.com/shahryarunity/maven.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install -DskipTests'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Code Analysis') {
            steps {
                sh 'echo "Running static code analysis..."'
            }
        }
    }
}
