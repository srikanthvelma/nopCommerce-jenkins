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
        stage('build') {
            steps{
                dotnetPublish outputDirectory : './target/nop.zip'
                dotnetTest project : './src/Tests',
                           outputDirectory: './target',
                           logger: 'junit;LogFilePath=test-result.xml'
            }
        }
        
    }
    
}