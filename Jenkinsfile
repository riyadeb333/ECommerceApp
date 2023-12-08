pipeline {
    agent any
    
    tools {
        maven 'M3'
        jdk 'jdk-17.0.7'
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/riyadeb333/ECommerceApp'
            }
        }
        
        stage('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage('Build') {
            steps { 
                    bat 'mvn install'
                }
            
        }
        
        // stage('Test') {
        //     steps {
        //         dir('backend') {
        //             sh 'mvn test'
        //         }
        //     }
        // }
        
        stage('Package') {
            steps {
               {
                    bat 'mvn package'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying..'
            }
        }
    }
}
