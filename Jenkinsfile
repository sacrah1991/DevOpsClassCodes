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
                    sh '-P metrics pmd:pmd --reportfile **/*.xml --exclude vendor/ || exit 0'
                pmd canRunOnFailed: true, pattern: '**/*.xml'
                }
            }
        
            stage('test'){
                steps{
                    sh 'mvn test'
                }
                steps{
                    sh 'pwd'
                }
            } 
            stage('package'){
                steps{
                    sh 'mvn package'
            }    
        }
    }

}
