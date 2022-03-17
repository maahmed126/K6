pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
              sh 'mkdir -p k6_results' 
              sh '''k6 run --csv json=my_test_result.csv eworks.js'''
              sh 'cp -r /var/jenkins_home/workspace/k6-test/*.json  k6_results' 
            }
        }
    }
}
