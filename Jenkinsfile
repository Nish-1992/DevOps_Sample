pipeline {
    agent any
    //triggers {
      //  cron '* * * * *'
    //}
    parameters {
        password defaultValue: '1234', name: 'PASSWORD'
        }
    stages {
        stage('Git_Checkout') {
            steps {
                git branch: 'main', credentialsId: '99b0344a-6277-451b-8e38-7bca9acd7bd8', url: 'https://github.com/Nish-1992/DevOps_Sample.git'
            }
        }
        stage('Build') {
            steps {
                echo "This is a build stage"
                sh "echo mkdir TEST"
                sh "zip files.zip *"
                echo "the job name is $JOB_NAME"
                echo "Password is $PASSWORD" 
                
            }
        }
    }
    post {
         always {
            build 'maven-build'
         }
    }
}
