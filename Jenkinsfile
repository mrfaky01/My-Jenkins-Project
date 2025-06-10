pipeline {
    agent any

    // No 'tools' section is needed here, as your static site doesn't require specific tools like Node.js.
    // If you add linters or other build tools later that Jenkins needs to find, you might add a 'tools' section.

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out source code...'
                git branch: 'main', url: 'https://github.com/mrfaky01/My-Jenkins-Project.git'
            }
        }

        stage('Prepare/Build (Static)') {
            steps {
                echo 'No complex build step needed for simple static files. Preparing for deployment...'
                // Create the 'dist' directory first, then copy files into it.
                // This ensures the target directory exists for the 'cp' command.
                sh 'mkdir -p dist'
                // Explicitly copy your static website files into the 'dist' folder.
                sh 'cp index.html style.css script.js dist/'
            }
        }

        stage('Test (Static)') {
            steps {
                echo 'No explicit tests for this simple static site. Performing basic validation placeholder...'
                // For a static site, 'tests' could involve:
                // - HTML validation (e.g., using a linter like html-proofer)
                // - CSS linting (e.g., stylelint)
                // - JavaScript linting (e.g., ESLint, if you install Node.js on Jenkins later)
                // For now, this step will simply succeed.
                sh 'echo "Static file validation placeholder completed." && exit 0'
            }
        }

        stage('Deploy (Static)') {
            steps {
                echo 'Deployment step placeholder for static website. (You will add real deployment commands here)'
                // This is where you would add commands to deploy your 'dist' folder content.
                // Common options include:
                // - Copying to an S3 bucket (AWS)
                // - Deploying to a web server (like Nginx on an EC2 instance)
                // - Pushing to a static hosting service (Netlify, Vercel, GitHub Pages)
                // For now, this step will simply pass.
            }
        }
    }

    // Post-build actions: These run after all stages are complete (or if they fail).
    post {
        always {
            echo 'Cleaning up workspace...'
            // This step requires the "Pipeline Utility Steps" plugin to be installed in Jenkins.
            // If 'cleanWs()' still gives a 'NoSuchMethodError' after a Jenkins restart,
            // you can temporarily replace it with: sh 'rm -rf *'
            cleanWs()
            echo 'Workspace cleaned.'
        }
    }
}