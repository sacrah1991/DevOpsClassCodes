pipeline{
    agent any
    stages {
        stage('Compile'){
            steps{
                sh 'mvn compile'
            }
            stage('review'){
                steps{
                    sh 'pmd canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '*/pmd.xml', unHealthy: ''
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
