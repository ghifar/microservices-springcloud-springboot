pipeline {
    agent { 
    	docker { 
	    	image 'maven:3.3.3'
	    	args '-v /root/.m2:/root/.m2' 
    	} 
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'mvn -B -DskipTests clean package'
            }
        }
        // stage('test') {
        //     steps {
        //         sh 'mvn --version'
        //     }
        // }
        stage('deploy') {
            steps {
                sh 'mvn --version'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }

        
}