pipeline {
    agent any
    stages {
        stage ('package') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy approval'){
        input "Deploy to test?"
    }
        stage ('deploy') {
            steps {
                sh 'mvn deploy -DmuleDeploy'
            }
        }
    }
}