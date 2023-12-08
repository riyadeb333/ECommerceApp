 pipeline {
    agent any
    
    tools {
        maven 'M3'
        //jdk 'JDK 19.0.1'
    }
    
    stages {
        
        // stage('Initialize') {
        //     steps {
        //         sh '''
        //             echo "PATH = ${PATH}"
        //             echo "M2_HOME = ${M2_HOME}"
        //         '''
        //     }
        // }

        stage('Build') {
           steps {
                // Get some code from a GitHub repository
                git 'https://github.com/riyadeb333/ECommerceApp.git'

                // Run Maven on a Unix agent.
                sh "mvn install"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
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
