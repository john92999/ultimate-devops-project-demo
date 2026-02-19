pipeline{
    agent any
    stages {
        stage ('Source code download'){
            steps{
                git url: "https://github.com/john92999/ultimate-devops-project-demo.git", branch: "main"
            }
        }
        stage ('Build the docker'){
            steps{
                dir ('src/ad') {
                sh 'docker build -t pjwesley7/adservice:v1 .'
                }
            }
        }
        stage('Run the buit image'){
            steps{
                sh 'docker run -d -P pjwesley7/adservice:v1'
            }
        }
    }
}