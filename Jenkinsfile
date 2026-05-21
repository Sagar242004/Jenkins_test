



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
                sh 'sudo docker build -t my_react .'
            }
        }

        stage('Docker Run') {
            steps {
                sh 'sudo docker rm -f my_react_container || true'
                sh 'sudo docker run -d --name my_react_container -p 5173:5173 my_react'
            }
        }
    }
}
