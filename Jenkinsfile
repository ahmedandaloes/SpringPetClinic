pipeline {
    agent any
    tools { maven 'M3' }
    
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ahmedandaloes/SpringPetClinic'
            }
        }
        
        stage('build') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'java -jar /home/coder/.jenkins/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
