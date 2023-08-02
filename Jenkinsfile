pipeline{
    agent any
    tools {maven 'M3'}
    
    stages{ 
        
        stage('checkout'){
            steps{
                
                git branch:'main', url:'https://github.com/arunksasi/SpringPetClinic.git', credentialsId: '093c8783-ad75-4095-9c8e-2bed18c61954'
                
           }
        }
        
        stage('build'){
            
            steps {
                sh 'mvn compile' 
                
            }
        
        }
        stage('test'){
            
            steps{
                
                sh 'mvn test' 
            }
        }
        
        stage('package'){
            
            steps{
                
                sh 'mvn package' 
            }
        }
        
        
        
        stage ('deploy'){
            
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/MavenScriptedProject/target/*.jar'
            }
        }
    }
}
