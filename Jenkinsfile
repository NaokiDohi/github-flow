pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echo 'Building..'
                // composer install # php
                // pip install -r requirements.txt # Python
                // npm install # node.js
                // etc.
                sh 'chmod +x test.sh'
            }
        }
        stage('Test') { 
            steps {
                sh './test.sh'
            }
        }
        stage('Deploy to staging') { 
            when {
                branch 'dev'
            }
            steps {
                echo 'Deploying to staging'
            }
        }
        stage('Deploy to production') { 
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to production'
            }
        }
    }
}
