pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Fetch the code from the main branch of GitHub
                git branch: 'main', url: 'https://github.com/Slimdrissi123/timesheet-devops.git'
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
                // Define Maven tool
                def mvn = tool 'Default Maven'
                
                // Execute SonarQube analysis
                withSonarQubeEnv() {
                    sh "${mvn}/bin/mvn sonar:sonar"
                }
            }
        }
    }
}
