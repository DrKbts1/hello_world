pipeline {
	agent any

    	parameters {
	    string(defaultValue: 'Daria', name: 'USERNAME')
	    booleanParam(defaultValue: true, description: '', name: 'runDefault')
        }
    stages {
    stage('Clone repository') {
	steps {
	checkout scm
	}

    }

    stage('Build and run image') { 
	steps {
	  script {
		sh 'touch logs.txt'
		sh 'docker build -t hello-world:latest -t hello-world:$BUILD_NUMBER .'
		if (params.runDefault) {
		    sh 'docker run hello-world:latest | tee logs.txt'
                } else {
		    sh 'docker run -e USERNAME=$USERNAME hello-world:latest | tee logs.txt'
                }
	} 
	archiveArtifacts artifacts: 'logs.txt'
	cleanWs deleteDirs:true
	}
    }
    

        }
    }
