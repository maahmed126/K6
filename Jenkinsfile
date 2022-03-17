       pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
              sh 'mkdir -p k6_results' 
              sh '''k6 run --out json=my_test_result.json eworks.js'''
              sh 'cp -r /var/jenkins_home/workspace/k6-test/*.json  k6_results' 
            }
         post {
             always { 
              cucumber jsonReportDirectory: 'k6_results' ,
              fileIncludePattern: 'k6_results/*.json',
              buildStatus: "UNSTABLE"

        }
    }
        }
    }
}
