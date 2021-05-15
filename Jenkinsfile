
node {
    stage('build'){
        withMaven (maven: 'maven3'){
            sh 'mvn clean install'    
        }
    }
}
stage('Deploy approval'){
    input "Deploy to prod?"
}
node {
    stage('deploy to prod'){
                sh 'mvn deploy -DmuleDeploy'
    }
}