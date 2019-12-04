pipeline{
    agent any
    stages {
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
            stage('review'){
                steps{
                    sh 'mvn -P metrics pmd:pmd'
                }
            }
        }
            stage('test'){
                steps{
                    sh 'mvn test'
                }
            } 
            stage('package'){
                steps{
                    sh 'mvn package'
            }    
        }
    }

}
