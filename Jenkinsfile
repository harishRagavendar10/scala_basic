pipeline{
    agent any
    tools{
        sbt 'sbt-1.9.7'
    }
    stages{
        stage("Checkout"){
            steps{
                checkout scm
            }
        }
        stage("Build"){
            steps{
                 sh 'sbt clean compile package'
            }

        }
    }
}