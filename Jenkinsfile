pipeline {
    agent any
    
    node {
        stage ('package') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    stage('Deploy approval'){
        input "Deploy to test?"
    }
    
    node {
        stage ('deploy') {
            steps {
                sh 'mvn deploy -DmuleDeploy'
            }
        }
    }    
}