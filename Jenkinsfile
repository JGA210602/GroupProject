pipeline {
    agent any
    stage('build') {
        steps {
            bat 'npm install json-server'
        }
    }
    stage('deploy') {
        steps {
            bat 'npm start'
            bat 'npx json-server src/database/Properties.json'
            bat 'npx json-server src/database/Sellers.json'
        }
    }
}