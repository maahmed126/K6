pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
              sh '''k6 run --out json=my_test_result.json eworks.js'''
            }
        }
    }
}
