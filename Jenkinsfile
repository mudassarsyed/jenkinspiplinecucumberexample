pipeline {
    agent any
    stages {
            stage('Execute')
            {
                steps {
                        {
                            sh 'mvn test'
                        }
                }
            }
            stage('Cucumber Reports')
             {
                 steps {
                         cucumber buildStatus:"UNSTABLE",
                         fileIncludePattern: "**/cucumber.json",
                         jsonReportDirectory: "reports/tests/cucumber/json"
                        }
             }
            }
    }