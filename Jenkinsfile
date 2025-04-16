pipeline {
    agent any

    stages {
        stage('build') {

            agent{
                docker{
                    image 'node:18-alpine'
                    resudeNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
