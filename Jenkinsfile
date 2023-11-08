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
                echo "You are running on service ${GLOBAL_ENVIRONMENT}" //? accessing values from GLOBAL_ENVIRONMENT
            }
        }
        stage('Test') {
            agent { 
                node {
                    label 'master' //todo use agent only in this 'Test' stage
                }
            }
            environment {
                STAGE_ENVIRONMENT = 'Stage Environment'
            }
            steps {
                echo "This is Test Stage"
                echo "This is ${STAGE_ENVIRONMENT}" //? accessing values from STAGE_ENVIRONMENT
            }
        }
        stage('UAT') {
            steps {
                echo "This is UAT Stage"
                //! echo "STAGE_ENV : ${STAGE_ENVIRONMENT}" // accessing values from different stages, it produces an error. don't use this!
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
