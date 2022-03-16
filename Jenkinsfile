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
              buildStatus: "UNSTABLE",
              "pretty", 
             "html:k6_results/cucumber", //this is telling cucumber to create a folder called cucumber
             "json:k6_results/cucumber", //this is also telling cucumber to create a folder called cucumber 
                            //even though you just need a file called cucumber.json
             "com.cucumber.listener.ExtentCucumberFormatter: target/report.html" 
    //there is an unnecessary white space before "target" that is causing another issue

        }
    }
        }
    }
}
