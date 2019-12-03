pipeline {
    agent any

    stages {
        stage ('Build') {
            steps {
                sh 'mvn compile'
            }
        }

        stage ('Review') {
            steps {
                sh '-P metrics pmd:pmd --reportfile **/*.xml --exclude vendor/ || exit 0'
                pmd canRunOnFailed: true, pattern: '**/*.xml'
            }
        }


        stage ('Test') {
            steps{
                sh 'mvn test'
                junit 'target/surefire-reports/*.xml'
            }
        }
        
        stage('Example') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
    

    
                
            
        
        stage ('package'){
            steps {
                echo "Building war file"
                sh 'mvn package'
                archiveArtifacts artifacts : 'target/*.war'
            }
        }

    }
}
