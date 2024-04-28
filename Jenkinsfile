pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            agent { label 'master' }
            steps {
                git 'https://github.com/RayItern/DevOpsCodeDemo-1.git'
            }
        }
        stage('Compile') {
            agent { label 'master' }
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Code Review') {
            agent { label 'slave1' }
            steps {
                // Execute your code review process here
                sh 'echo "Executing code review"'
            }
        }
        stage('Unit Testing') {
            agent { label 'slave1' }
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            agent { label 'master' }
            steps {
                sh 'mvn package'
            }
        }
    }
}
