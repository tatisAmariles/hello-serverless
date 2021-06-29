pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                nodejs(nodeJSInstallationName: 'nodejs'){
                echo '**************************** Install all project dependencies**********************************'
                sh 'npm install'
                
                }
            }
        } 
        stage('test'){
            steps{
                echo '****************************Testing ****************************'               
            }
        }
        stage('deploy'){
            steps{
                nodejs(nodeJSInstallationName: 'nodejs'){
                    withAWS(credentials: 'aws-credentials'){
                        echo '****************************deploy ****************************'  
                        sh 'serverless deploy'
                    }
                }
            }
    
        }
    }
}