pipeline {
    agent any
    
    tools {
        maven 'Maven 3.9.2'
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
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage('Build') {
            steps {
                dir('backend') {
                    sh 'mvn clean install -DskipTests'
                }
            }
        }
        
        stage('Test') {
            steps {
                dir('backend') {
                    sh 'mvn test'
                }
            }
        }
        
        stage('Package') {
            steps {
                dir('backend') {
                    sh 'mvn package'
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
