pipeline {
    agent { label 'UBUNTU_NODE3'}
    stages {
        stage('vcs'){
            steps {
                git url: 'https://github.com/srikanthvelma/nopCommerce-jenkins.git',
                    branch: 'declarative'
            }
        }
        stage('build') {
            steps {
                sh 'dotnet build ./src/NopCommerce.sln'
            }
        }
        stage('test') {
            steps {
                sh 'dotnetPublish ./src --output ./publish'
                sh 'dotnetTest ./src --logger:"junit;LogFilePath=test-result.xml"'
            }
        }
        
    }
    
}