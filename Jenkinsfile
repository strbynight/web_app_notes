pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Checkout Code') {
            steps {
                cleanWs()
                checkout scm
            }
        }

        stage('Docker Deploy') {
            steps {
                echo 'Перезапускаем контейнеры команды project_05...'
                sh 'docker compose -p project_05 down'
                sh 'docker compose -p project_05 up -d --build'
            }
        }
    }
}