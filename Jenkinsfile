pipeline {
    agent any
    
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
               bat'mvn clean package'
            } 
             post {
                 success {
                     echo 'Now Archiving...'
                     archiveArtifacts artifacts:'**/target/*.war'
                 }
             }
        }  
    } 
 }
