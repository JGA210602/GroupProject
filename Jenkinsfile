pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'npm install json-server'
            }
        }
        stage('deploy') {
            steps {
                parallel (
                    a: {bat 'npx json-server src/database/Properties.json --port 8000'},
                    b: {bat 'npx json-server src/database/Sellers.json --port 8001'},
                    c: {bat 'npm start'}
                )
            }
        }
    }
}