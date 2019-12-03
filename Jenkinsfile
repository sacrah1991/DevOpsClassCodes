pipeline{
    agent{
        label "any"
    }
    stages{
        stage("Compile"){
            steps{
                echo "Compiling the code"
                mvn 'compile'
            }
        }
    }
}
