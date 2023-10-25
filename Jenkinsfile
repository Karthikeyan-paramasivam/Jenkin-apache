pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                script {
                    sshPublisher(
                        continueOnError: false,
                        failOnError: true,
                        publishers: [
                            sshPublisherDesc(
                                configName: 'YourSSHConfig',
                                transfers: [
                                    sshTransfer(
                                        execCommand: "./deploy.sh", // Path to your deployment script
                                        execTimeout: 120000,
                                    )
                                ]
                            )
                        ]
                    )
                }
            }
        }
    }
}
