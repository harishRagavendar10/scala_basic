pipeline{
    agent any
    parameters{
        booleanParam(name: 'RUN_TEST', defaultValue: true, description: 'Run test?')
        choice(name: 'ENV' , choices: ['DEV','PROD','PP'], description: 'enviroment')
    }
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
        stage("Test"){
            when{
                expression{
                    params.RUN_TEST
            }
            }
            steps{
                sh 'sbt test'
            }
        }
    }

}



