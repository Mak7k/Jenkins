pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building…'
                // Шаги сборки
            }
        }

        stage('Test') {
            steps {
                echo 'Testing…'
                // Шаги тестирования
            }
        }
    }

    post {
        // Блок, который выполнится после завершения всех этапов
        failure {
            // Действия при провале сборки
            echo "Сборка завершилась с ошибкой"
            mail to: 'mak7ka01@gmail.com',
                 subject: "${env.JOB_NAME} – Сборка № ${env.BUILD_NUMBER} провалилась",
                 body: "Для получения информации проверьте вывод по адресу: ${env.BUILD_URL}"
        }
    }
}
