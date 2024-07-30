pipeline{
    agent any
    
    stages{
        stage ("compile"){
            steps{
            bat 'javac Main.java'
            }
        }
        stage ("run"){
            steps{
            bat 'java Main.java'
            }
        }
    }
     post {
        success {
            echo 'Pipeline completed successfully!'
            // Send email notification
            emailext (
                subject: "Build Successful: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Good news! The build was successful.\n\nCheck it out here: ${env.BUILD_URL}",
                recipientProviders: [[$class: 'CulpritsRecipientProvider'], [$class: 'RequesterRecipientProvider']],
                to: 'ashwamedh.datta@ltts.com' // Replace with your recipient email
            )
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
