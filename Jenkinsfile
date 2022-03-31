pipeline {
    agent any
    
   tools{
        maven 'M2_HOME'
    }
    
    stages{
        
        stage("checkout") {
          steps{
           checkout([$class: 'GitSCM', branches: [[name: '*/Test']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sravz8184/DevopsBasics.git']]]) 
            }
          }
        
        stage("build") {
          steps{
            sh 'mvn clean install package'
          } 
           /* post{
                success{
                    archiveArtifacts 'target/*.war'
                }
            } */
        }
        
       /* stage("test") {
            steps{
             sh 'mvn test'   
            }
        }
        stage("package") {
            steps{
             sh 'mvn package'        
            }
            post{
                success{
                    archiveArtifacts 'target/*.war'
                }
            }
        }
   /*     stage("Build Docker Image") {
            steps{
             script{
                  
                 bat 'docker build -t sravz408/my-app:latest .'
                }
            }
        }
        stage("Push docker Image") {
            steps{
                script{
                    withCredentials([string(credentialsId: 'dockerhubp', variable: 'dockerhub')]) {
                    bat 'docker login -u sravz408 -p ${dockerhubp}'
                    
}
                    bat 'docker push sravz408/my-app:latest'
}
               
               
            }
        } */
        
        
        
    }
    
}
