pipeline {

    agent any
    stages {
        stage('Checkout') {
            steps { //Checking out the repo
                sh 'gradle test -Dnum.parallels=20'
            }
        }
        stage('Publish Artifact to Nexus') {
            steps {
                cucumber buildStatus:"UNSTABLE",
                fileIncludePattern: "**/cucumber.json",
                jsonReportDirectory: "reports/tests/cucumber/json"
            }
        }
    }
}