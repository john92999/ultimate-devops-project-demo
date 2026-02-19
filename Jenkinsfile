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
                dir ('ultimate-devops-project-demo/src/product-catalog') {
                sh 'docker build -t pjwesley7/product-catalog:v1 .'
                }
            }
        }
        stage('Run the buit image'){
            steps{
                sh 'docker run pjwesley7/product-catalog:v1'
            }
        }
    }
}