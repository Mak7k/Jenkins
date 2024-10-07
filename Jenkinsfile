pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building…'
                // Здесь выполняются шаги сборки
                sh 'exit 0' // Пример успешной сборки
            }
        }

        stage('Test') {
            steps {
                echo 'Testing…'
                // Здесь выполняются шаги тестирования
                sh 'exit 1' // Пример неудачного тестирования (для проверки failure)
            }
        }
    }

    post {
        // Действия после завершения всех этапов
        success {
            echo "Сборка успешна"
            mail to: 'mak7ka01@gmail.com',
                 subject: "${env.JOB_NAME} – Сборка № ${env.BUILD_NUMBER} успешна",
                 body: "Сборка прошла успешно. Результаты доступны по адресу: ${env.BUILD_URL}"
        }
        failure {
            echo "Сборка завершилась с ошибкой"
            mail to: 'mak7ka01@gmail.com',
                 subject: "${env.JOB_NAME} – Сборка № ${env.BUILD_NUMBER} провалилась",
                 body: "Сборка завершилась с ошибкой. Для получения информации проверьте вывод по адресу: ${env.BUILD_URL}"
        }
    }
}
