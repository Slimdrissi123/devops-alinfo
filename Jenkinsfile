pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Fetch the code from the master branch of GitHub
                git branch: 'main', url: 'https://github.com/bedirlouka/test-jenkins.git'
            }
        }
        
        
        stage('Compile') {
            steps {
                // Compile the Maven project
                sh 'mvn compile'
            }
        }
        
        stage('SonarQube analysis') {
            steps {
               
               
                    sh 'mvn sonar:sonar '
                
            }
        }
        
    }
}
