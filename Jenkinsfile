pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
              sh '''k6 run --out html=my_test_result.html eworks.js'''
            }
        }
    }
}
