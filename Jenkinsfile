pipeline
{
    options
    {
        skipDefaultCheckout()
    }
    agent
    {
        node
        {
            customWorkspace('first-maven-project')
            label 'slave2'
        }
    }
    tools
    {
        maven 'maven_3.6.3'
    }
    stages
    {
        stage('Pulling_GitHub_repo')
        {
            steps
            {
                checkout scmGit(branches: [[name: 'stable-2.289']],
                userRemoteConfigs: [
                    [ url: 'https://github.com/jenkinsci/jenkins.git' ]
                ])
            }
            
        }
        stage('maven_build')
        {
            steps
            {
                sh 'mvn -v'
            }
        }
    }
}