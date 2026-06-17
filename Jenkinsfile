pipeline {
    agent any 

    tools {
        maven 'Maven' 
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/omkar183/MyMavenApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  
            }
        }
        stage('Run Application') {
            steps {
                sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }     
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
