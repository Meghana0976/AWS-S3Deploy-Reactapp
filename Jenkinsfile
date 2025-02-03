pipeline {
    agent any
    tools {
        nodejs 'nodejs'
    }

    stages {
        stage('Git Checkout') {
            steps {
               git url:"https://github.com/Meghana0976/AWS-S3Deploy-Reactapp.git",branch:"main"
            }
        }
        stage('NPM install'){
            steps{
                sh "npm install"
            }
        }
        stage('Node Build'){
            steps {
                sh "npm run build"
            }
        }
      

        stage('S3 Deploy'){
            steps{
                sh "aws s3 sync dist/ s3://s3-react-app --delete"
            }
        }
    }
}
