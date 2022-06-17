def scheme = 'JenkinsStudy'

pipeline {
    agent any
    parameters {
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'main', name: 'branch', type: 'PT_BRANCH' 
    }

    stages {
        stage('Setup') {
            steps {
                git branch: "${params.branch}", url: 'https://github.com/0lefirenko/JenkinsStudy.git'
                echo '${params.branch}'
            }
        }
        stage('Build') { 
            steps {
                sh "fastlane build"
            }
        }
        stage('Test') { 
            steps {
            	echo '${params.branch}'
            }
        }
    }
}