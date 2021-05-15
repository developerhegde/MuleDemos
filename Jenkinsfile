
node {
    stage('build'){
        withMaven (maven: 'maven3'){
            sh 'mvn clean package deploy -DmuleDeploy'    
        }
    }
}
