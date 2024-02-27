pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                bat 'npm i'
                bat 'npm run build'
            }
        }
        stage('deploy') {
            steps {
                parallel (
                    a: {bat 'npx json-server src/database/Properties.json --port 8001'},
                    d: {bat 'npm start'}
                )
            }
        }
    }
}