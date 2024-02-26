pipeline{
    
    agent any
    
    stages{
         stage('Clone the repo')
        {
            steps{
            git branch: 'nodejs', url: 'https://github.com/Jahnavi4895/MultiBranchDeployment.git'
            }
        }
        stage('Build Image')
        {
            steps{
                sh 'docker build -t myappnodejs:$BUILD_NUMBER .'
            }
        }
        stage('Deploy the Image')
        {
            steps{
                sh 'docker run -d -P myappnodejs:$BUILD_NUMBER'
                sh 'docker ps'
            }
        }
        
    }
}
