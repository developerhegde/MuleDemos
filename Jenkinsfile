node {
    stage('build'){
        withMaven(maven: 'maven3'){
            sh 'mvn clean package'
        }
        
    }
}

node {
    stage('test'){
        echo 'Test Started'
        withMaven (maven: 'maven3'){
            sh 'mvn test'    
        }
        post {
            always {
                junit '**/target/surefire-reports/TEST-*.xml'
            }
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
