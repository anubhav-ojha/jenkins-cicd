pipeline {
    agent any

    environment {
        MESSAGE = 'Jenkins Declarative Pipeline'
    }

    parameters {
        string(name: 'USERNAME', defaultValue: 'anubhav', description: 'Your name')
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/anubhav-ojha/jenkins-cicd.git'
            }
        }

        stage('Permission') {
            steps {
                sh 'chmod +x hello.sh'
            }
        }

        stage('Run Script') {
            steps {
                sh './hello.sh'
            }
        }

        stage('Print Info') {
            steps {
                echo "User: ${params.USERNAME}"
                echo "Env Message: ${env.MESSAGE}"
            }
        }
    }

    post {
        success {
            echo "✅ Build completed successfully"
        }
        failure {
            echo "❌ Build failed"
        }
    }
}
