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

        stage('Test'){
            steps
            {
                sh 'mvn test'
            }
        }
        stage('build'){
            steps
            {
                sh 'mvn package'
            }
        }
        stage('push Docker Image'){
            steps{
                withDockerRegistry([credentialsID: "dockerhub", url:""])
                {
                    sh 'docker push jsachdev07/abc_tech:$BUILD_NUMBER'
                }
            }
        }
        stage('deploy as container'){
            steps{
                sh 'docker run -itd -P jsachdev07/abc_tech:$BUILD_NUMBER'
            }
        }
    }
}