pipeline {
    agent any
 tools {
        maven 'maven_3.5.3'
    }
    
    stages {
/*        stage('Init') {
            steps {
                echo "Testing..."
            }
        }
        stage('Build') {
            steps {
                echo "Building..."
            }
        }
        stage('Deploy') {
            steps {
                echo "Code deployed"
            }
        }*/
          stage('Build') {
            steps {
               bat 'mvn clean package'
            } 
             post {
                 success {
                     echo 'Now Archiving...'
                     archiveArtifacts artifacts:'**/target/*.war'
                 }
             }
        }
        stage('Deploy to Staging') {
            steps {
              build job: 'deploy-to-staging'
            } 
      }   
    } 
 }
