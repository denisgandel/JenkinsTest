pipeline {
  agent any
    
  stages {
      stage('Clone') {
          steps {
              git clone 'https://github.com/denisgandel/JenkinsTest.git'
          }
        }
        
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                sh 'npm run build'
            }
        }
    }
}