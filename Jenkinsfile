pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Fetch the code from the master branch of GitHub
                git branch: 'main', url: 'https://github.com/Slimdrissi123/devops-alinfo.git'
            }
        }
        
        
        stage('Compile') {
            steps {
                // Compile the Maven project
                sh 'mvn clean compile'
            }
        }
        
        stage('SonarQube analysis') {
            steps {
               
               
                    sh 'mvn clean sonar:sonar '
                
            }
        }
        
    }
}
