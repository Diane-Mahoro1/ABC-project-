pipeline 

{
    agent any 
    stages 
    {
        stage('Code checkout')
        {
            steps 
            {
                git branch: 'main', url: 'https://github.com/Diane-Mahoro1/ABC-project-.git'
            }
        }
        stage('code compile'){
            steps
            {
                sh 'mvn compile'
            }

        }
        stage('Code packaging'){
            steps
            {
                sh 'mvn package'
            }
        }
    }
}