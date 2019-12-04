pipeline{
    agent any
    stages {
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
        }
            stage('test'){
                steps{
                    sh 'mvn test'
                }
            } 
            stage('unit test'){
                steps{
                    sh 'mvn cobertura:cobertura -Dcobertura report format=xml'
            }    
        }
    }

}
