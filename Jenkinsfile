node {
    stage('build'){
        withMaven(maven: 'maven3'){
            sh 'mvn clean install -DskipTests'
        }
        
    }
}

node {
    stage('test'){
        echo 'Test Started'
        withMaven (maven: 'maven3'){
            sh 'mvn test'    
        }
    }
}

stage('Deploy approval'){
    input "Deploy to prod?"
}
node {
    stage('deploy-to-prod'){
        withMaven(maven: 'maven3'){
            sh 'mvn deploy -DmuleDeploy'
        }
    }
}
