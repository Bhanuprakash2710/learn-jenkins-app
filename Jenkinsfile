pipeline {
    agent any

    stages {
        stage('build') {

            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    rm -rf node_modules package-lock.json
                    npm cache clean --force
                    npm install
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
