pipeline 
{
    agent any

    stages 
    {   
         stage ('Stop Container') 
        {
            steps 
            {
               script{
                    sh 'docker stop web'
                }
            }
        }
        
        stage ('Remove Container') 
        {
            steps 
            {
                script {
                    sh 'docker rm web'
                }
            }
        }
         stage ('Remove Container Image') 
        {
            steps 
            {
                script {
                    sh 'docker rmi image '
                }
            }
        }
        stage ('Build docker image') 
        {
            steps 
            {
                script{
                    sh 'docker build -t image .'
                }
            }
        }
        stage('Build docker Container') 
        {
            steps 
            {
                script{
                    sh 'docker run -d --name web -p 8282:80 image '
                }
            }
        }
    }
    
}