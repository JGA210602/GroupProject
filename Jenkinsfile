pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'npm install json-server'
            }
        }
        stage('deploy') {
            parallel {
                stage('Deploy json-server'){
                    steps {
                        bat 'npx json-server src/database/Properties.json --port 8000'
                        bat 'npx json-server src/database/Sellers.json --port 8001'
                    }
                }
                stage('Run app'){
                    steps {
                        bat 'npm start'
                    }
                }
            }
        }
    }
}