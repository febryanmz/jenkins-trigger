pipeline {
    agent {
        label 'master'
    }
    environment {
        GLOBAL_ENVIRONMENT = 'Test-Service'
    }
    stages {
        stage('Development') {
            steps {
                echo 'You are running on service {$GLOBAL_ENVIRONMENT}'
                echo 'This is Development Stage'
            }
        }
        stage('Test') {
            steps {
                echo 'This is Test Stage'
            }
        }
        stage('UAT') {
            steps {
                echo 'This is UAT Stage'
            }
        }
    }
    post {
        success {
            echo 'Jenkins Pipeline successfully executed!'
        }
        failure {
            error('Jenkins Pipeline execution failed!')
        }
    }
}