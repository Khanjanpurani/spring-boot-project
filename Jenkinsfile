pipeline {
    agent any
    
    tools {
        maven "Maven 3.x" 
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Khanjanpurani/spring-boot-project.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package' 
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test' 
            }
        }
        stage('Package') {
            steps {
                bat 'mvn package' 
            }
        }
        stage('Deploy to localhost:5000') {
            steps {
                 bat 'mvn spring-boot:run &'
                 bat 'sleep 10'
            }
        }
    }
}
