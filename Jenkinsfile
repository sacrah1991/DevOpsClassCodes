pipeline{
    agent{
        label ("master")
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
