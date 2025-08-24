pipeline{
    
    agent any  
    
    tools{
        maven 'mymaven'
    }
    
    stages{
        
        stage('Checkout code '){
            steps{
                
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
                
            }
        }
        
         stage('compile code '){
            steps{
                
                sh 'mvn compile'
                
            }
        }
        
        stage('Test code '){
            steps{
                sh 'mvn test'
            }
        }
        
        stage('Package code '){
            steps{
                
                sh 'mvn package'
                
            }
        }

        
    }
}

