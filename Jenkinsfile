
node {
    stage('test'){

    	echo 'Test Started'
=======
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
