pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
              sh 'mkdir -p k6_results' 
              sh '''k6 run --out csv=test_result.csv eworks.js'''
              sh 'cp -r /var/jenkins_home/workspace/k6-test/*.csv  k6_results' 
            }
             post {
        always {

                publishHTML([allowMissing: false,
                      alwaysLinkToLastBuild: true,
                      keepAll: true,
                      reportDir: 'k6_results',
                      reportFiles: 'test_result.csv',
                      reportName: 'K6-Report',
                      includes: 'test_result.csv'
     ])        
            }
        }
        }
    }
}
