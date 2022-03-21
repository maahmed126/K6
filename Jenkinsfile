pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
              sh 'mkdir -p k6_results' 
              sh '''k6 run --out json=test_result.json eworks.js'''
              sh 'cp -r /var/jenkins_home/workspace/k6-test/*.json  k6_results' 
            }
             post {
        always {

                publishHTML([allowMissing: false,
                      alwaysLinkToLastBuild: true,
                      keepAll: true,
                      reportDir: 'k6_results',
                      reportFiles: 'test_result.json',
                      reportName: 'K6-Report',
                      includes: 'test_result.json'
     ])        
            }
        }
        }
    }
}
