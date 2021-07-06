pipeline {
    agent any
    stages {
            stage('Execute')
            {
                steps {
                        withMaven(maven: 'Maven3_5_4') {
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