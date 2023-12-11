pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ayesha-eiman-bukhari/ayesha-bukhari876.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'MyServer',
                            transfers: [sshTransfer(sourceFiles: '**/*', remoteDirectory: '/myapp/')],
                            
                        )
                    ]
                )
            }
        }
    }
}
