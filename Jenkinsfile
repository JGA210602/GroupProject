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
                    a: {bat 'npx json-server groupproject/src/database/Properties.json --port 8000'},
                    b: {bat 'npx json-server groupproject/src/database/Sellers.json --port 8001'},
                    c: {bat 'cd groupproject'}
                    d: {bat 'npm start'}

                )
            }
        }
    }
}