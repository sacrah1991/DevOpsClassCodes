pipeline{
    agent any
    stages {
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
        }
            stage('review'){
                steps{
                    sh 'mvn -P metrics pmd:pmd'
                }
            }
        
            stage('test'){
                steps{
                    sh 'mvn test'
                }
            } 
            stage('unit test'){
                steps{
                    sh 'cobertura:cobertura -Dcobertura report format=xml'
                }
            }
            stage('package'){
                steps{
                    sh 'mvn package'
            }    
        }
    }

}
