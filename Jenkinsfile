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
                        to: 'amineayadi286@gmail.com',
                        subject: "New Commit in Repo",
                        body: "Contents of Readme.txt:\n\n${content}"
                    )
                }
            }
        }
    }
}
