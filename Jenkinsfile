pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                 checkout scm
            }
        }
        stage('Send Email') {
            steps {
                script {
                    def content = readFile 'Readme.txt'
                    emailext (
                        to: 'jrssjtrunksjr@gmail.com',
                        recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']],
                        subject: "New Commit in Repo",
                        body: "Contents of Readme.txt:\n\n${content}"
                    )
                }
            }
        }
    }
}
