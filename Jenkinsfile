
pipeline {
	agent { label 'linux' }
	stages {
	stage('Unit Tests') {
	    steps {
		git 'https://github.com/siva9923/java-project.git'
		sh 'ant -f test.xml -v'  
	    }
	}   
	stage('Build') {    
	    steps {
		sh 'ant -f build.xml -v'   
	    }
	}   
	stage('Deploy') {  
	    steps {  
		sh 'echo in deploy step' 
		junit 'reports/result.xml'
	    }
	}
}
}
