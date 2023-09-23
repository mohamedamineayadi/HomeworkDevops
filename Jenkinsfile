pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                mvn --version
            }
        }
        stage('Send Email') {
            steps {
                script {
                    def content = readFile 'Readme.txt'
                    emailext (
                        to: 'jrssjtrunksjr@gmail.com',
                        subject: "New Commit in Repo",
                        body: "Contents of Readme.txt:\n\n${content}"
                    )
                }
            }
        }
    }
}
