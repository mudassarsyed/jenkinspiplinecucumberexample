pipeline {

    agent any
    stages {
        stage('Checkout') {
            steps { //Checking out the repo
                sh './gradlew test'
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
