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
                //sh 'dotnet publish ./src/NopCommerce.sln --output ./publish'
                sh 'dotnet test ./src/NopCommerce.sln --logger:"junit;LogFilePath=test-result.xml"'
            }
        }
        
    }
    
}