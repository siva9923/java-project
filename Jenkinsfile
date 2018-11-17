
pipeline {
	agent { label 'linux' }
	stages {
	stage('Unit Tests') {
	    steps {
		git 'https://github.com/siva9923/java-project.git'
		sh 'ant -f test.xml -v'  
		junit 'reports/result.xml'
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
		sh 'aws s3 mb s3://mybucket --region us-east-1'
		sh 'aws s3 cp dist/rectangle*.jar s3://mybucket/'
		
	    }
	}
}
}
