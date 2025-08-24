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
                    deploy adapters: [tomcat9(credentialsId: 'tomcatserver', path: '', url: 'http://localhost:9090/')], contextPath: null, war: '**/*.war'
                }
            }

        }

        
    }
}

