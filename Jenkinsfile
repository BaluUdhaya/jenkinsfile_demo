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
            post{
                success{
                    deploy adapters: [tomcat9(credentialsId: 'b559ea7f-d7f5-49e4-b0f2-0192e3e25690', path: '', url: 'http://localhost:9090')], contextPath: null, onFailure: false, war: '**/*.war'
        }
            }
        }
    }
}

