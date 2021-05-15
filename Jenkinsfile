node {
    stage('build'){
            sh 'mvn clean package'
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
