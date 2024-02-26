pipeline{
    tools{
        maven 'mymaven'
    }
    agent any
    
    stages{
        stage('Clone the repo')
        {
            steps{
            git branch: 'html', url: 'https://github.com/Jahnavi4895/MultiBranchDeployment.git'
            }
        }
        stage('Build Image')
        {
            steps{
                sh 'docker build -t myapphtml:$BUILD_NUMBER .'
            }
        }
        stage('Deploy the Image')
        {
            steps{
                sh 'docker run -d -P myapphtml:$BUILD_NUMBER'
                sh 'docker ps'
            }
        }
        
    }
}
