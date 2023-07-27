pipeline
{
    /*options
    {
        skipDefaultCheckout()
    }*/
    agent
    {
        node
        {
            customWorkspace('first-maven-project1')
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
                checkout scmGit(branches: [[name: 'origin/master']],
                userRemoteConfigs: [
                    [ url: 'https://github.com/uriyapraba/myfirst-project.git' ]
                ])
            }
            
        }
        stage('maven_build')
        {
            steps
            {
                sh 'mvn clean package'
            }
        }
    }
}