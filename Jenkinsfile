pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Prince730-creator/pro1'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with ashish'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with ashish'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with ashish'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with ashish'){
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
                sh 'docker run -dt -p 8092:8091 --name c001 myimg'
            }
        }   
    }
}
