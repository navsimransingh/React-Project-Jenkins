pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
    }
    post {
        success {
            emailext(
                subject: "Success: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """<p>Build successful!</p>
                        <p>Check console output at <a href='${env.BUILD_URL}'>${env.BUILD_URL}</a></p>""",
                to: 'navsimransingh786@gmail.com',
                cc: '',
                bcc: '',
                mimeType: 'text/html'
            )
        }
        failure {
            emailext(
                subject: "Failure: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: """<p>Build failed. Please check console output at <a href='${env.BUILD_URL}'>${env.BUILD_URL}</a></p>""",
                to: 'navsimransingh786@gmail.com',
                cc: '',
                bcc: '',
                mimeType: 'text/html'
            )
        }
    }
}
