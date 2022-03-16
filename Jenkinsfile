pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
              sh '''k6 run --out csv=my_test_result.csv eworks.js'''
            }
        }
    }
}
