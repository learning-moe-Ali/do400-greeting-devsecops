pipeline {
    agent { label 'nodejs' }

    environment { APP_NAMESPACE = 'mohamed-devsecops' }

    stages{

        stage('Test'){
            steps {
                sh "node test.js"
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    oc start-build greeting-devsecops \
                    --follow --wait -n ${APP_NAMESPACE}
                '''
            }
        }
    }
}
