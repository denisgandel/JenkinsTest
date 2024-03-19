pipeline {
  agent any
    
  stages {
      stage('Clone') {
          steps {
              echo 'Cloning'
              git clone 'https://github.com/denisgandel/JenkinsTest.git'
          }
        }
        
        stage('Install dependencies') {
            steps {
                echo 'Install dependencies'
                sh 'npm install'
            }
        }
        
        stage('Build') {
            steps {
                echo 'building'
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
              echo 'deploying'
                sh 'npm run dev'
            }
        }
    }
}