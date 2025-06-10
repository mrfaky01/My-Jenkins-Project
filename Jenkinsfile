pipeline {
    agent any // This means Jenkins can run the pipeline on any available agent (the EC2 instance itself, in this case)

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/mrfaky01/My-Jenkins-Project.git' // <-- IMPORTANT: Make sure this is YOUR exact repository URL
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your actual build commands here. Examples:
                // For Node.js: sh 'npm install'
                // For Java Maven: sh 'mvn clean install'
                // For Python: sh 'pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your actual test commands here. Examples:
                // For Node.js: sh 'npm test'
                // For Java Maven: sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment step placeholder. (You will add real deployment commands later)'
            }
        }
    }
}
