pipeline {
    agent any
stages {
    stage('build'){
        steps {
            withMaven (maven: 'maven3'){
            sh 'mvn clean package deploy -DmuleDeploy'    
        }
        }
    }
}
}
