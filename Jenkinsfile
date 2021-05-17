pipeline {
    agent any
    tools { 
        maven 'maven3'
    }
    stages {
        stage('build and test') {
            steps{
                sh 'mvn clean test'
            }
            post {
                always {
                    publishHTML (target : [allowMissing: false,
                        alwaysLinkToLastBuild: true,
                        keepAll: true,
                        reportDir: 'target/munit-reports',
                        reportFiles: 'myreport.html',
                        reportName: 'My Reports',
                        reportTitles: 'The Report'])
                }
            }
        }
    }
}
