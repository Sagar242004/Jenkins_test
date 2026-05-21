



pipeline {
    agent any

    triggers {
        cron('H/2 * * * *')
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Sagar242004/Jenkins_test.git'
            }
        }

        stage('Docker Build') {
            steps {
                sh ' docker build -t my_react .'
            }
        }

        stage('Docker Run') {
            steps {
                sh 'docker rm -f my_react_container || true'
                sh 'docker run -d --name my_react_container -p 5173:80 my_react'
            }
        }
    }
}
