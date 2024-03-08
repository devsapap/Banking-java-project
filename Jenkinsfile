pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/devsapap/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with srinivas'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with srinivas'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with srinivas'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with srinivas'){
            steps{
                sh 'mvn package'
            }            
        }
        stage('run dockerfile'){
            steps{
                sh 'docker build -t myimg .'
            }
        } 
        stage('port expose;){
              steps{
                  sh 'docker -dt -p 8085:80 --name c000 myimg'
              }    
       } 
    
 }
