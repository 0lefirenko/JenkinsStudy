def scheme = 'JenkinsStudy'

pipeline {
    agent any
    parameters {
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'main', name: 'branch', type: 'PT_BRANCH' 
        choice(name: 'scheme', choices: ['JenkinsStudy', 'JenkinsStudyProd'], description: '')
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
                sh "fastlane build scheme:${params.scheme}"
            }
        }
        stage('Test') { 
            steps {
            	sh "fastlane tests scheme:${params.scheme}"
            }
        }
    }
}