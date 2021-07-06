pipeline {
    agent any

    stages{
            stage('Execute')
            {
                steps {
                        withMaven(maven: 'Maven 3.5.4') {
                            sh 'mvn test'
                        }
                }
            }
            stage('Cucumber Reports')
                        {
                            steps {
                                    cucumber buildStatus:"UNSTABLE"
                                    fileIncludePattern: "**/cucumber.json"
                                    jsonReportDirectory: "reports/tests/cucumber/json"
                                    }
                            }
                        }
    }
}
}