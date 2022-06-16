pipeline {
    stages {
        stage('Build') { 
            steps {
		xcodebuild -scheme JenkinsStudy build    
            }
        }
        stage('Test') { 
            steps {
            	xcrun xcodebuild -scheme JenkinsStudy test 
            }
        }
    }
}