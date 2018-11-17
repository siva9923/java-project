
pipeline {
	agent { label 'linux' }
	stages {
	stage('Test') {
	    steps {
		git 'https://github.com/siva9923/java-project.git'
		sh 'ant -buildfile test.xml'   
	    }
	}   
	stage('Build') {    
	    steps {
		sh 'ant'   
	    }
	}   
	stage('Results') {  
	    steps {  
		junit 'reports/*.xml'   
	    }
	}
}
}
