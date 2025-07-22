pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'git@github.com:srthesmarty/express-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Restart Express App') {
            steps {
                sh 'pm2 delete express || true'
                sh 'pm2 start index.js --name express'
            }
        }
    }
}
