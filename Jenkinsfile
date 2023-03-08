pipeline {
    agent { label 'UBUNTU_NODE3'}
    triggers { pollSCM('* * * * *')}
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
        
    }
    
}