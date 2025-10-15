pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
    }

    post {
        success {
            emailext (
                subject: "Build Successful: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build completed successfully!",
                to: 'akashanchaneyalu@gmail.com',
                mimeType: 'text/html'
            )
        }
        failure {
            emailext (
                subject: "Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Please check the Jenkins logs for details.",
                to: 'akashanchaneyalu@gmail.com',
                mimeType: 'text/html'
            )
        }
    }
}
