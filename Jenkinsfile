pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Test') {
	tools {
        snyk 'mySnyk'
      }	
      steps {
        echo 'Testing...'
        snykSecurity(
          snykInstallation: 'mySnyk',
          snykTokenId: 'mySnkToken',
          // place other parameters here
 	  targetFile: 'req.txt',
	additionalArguments: '--package-manager=pip'
	  
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
