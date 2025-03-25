pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/HITESH9978/pro1'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with hitesh'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with hitesh'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with hitesh'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with hitesh'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
