pipeline{
    agent{
        label ("master")
    }
    stages{
        stage("Compile"){
            steps{
                echo "Compiling the code"
                sh "mvn compile"
            }
        }
    }
}
