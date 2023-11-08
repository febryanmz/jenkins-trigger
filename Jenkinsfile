pipeline {
    agent {
        label 'master'
    }
    environment {
        GLOBAL_ENVIRONMENT = 'Global Environment'
    }
    stages {
        stage('Development') {
            steps {
                echo "This is Development Stage"
                echo "You are running on service ${GLOBAL_ENVIRONMENT}"
            }
        }
        stage('Test') {
            agent {
                label 'master'
            }
            environment {
                STAGE_ENVIRONMENT = 'Stage Environment'
            }
            steps {
                echo "This is Test Stage"
                echo "This is ${STAGE_ENVIRONMENT}"
            }
        }
        stage('UAT') {
            steps {
                echo "This is UAT Stage"
                echo "I Will try to access STAGE_ENV : ${STAGE_ENVIRONMENT}" // You can't use this, because it is a different stage
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