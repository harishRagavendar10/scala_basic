pipeline{
    agent any
    parameters{
        string(name: 'githubBranch', defaultValue: 'DEVOPS-12', description: 'github branch')
        booleanParam(name: 'RUN_TEST', defaultvalue: true, description: 'Run test?')
        choice(name: 'ENV' , choices: ['DEV','PROD','PP'], description: 'enviroment')
    }
    tools{
        sbt 'sbt-1.9.7'
    }
    stages{
        stage("Checkout"){
            steps{
                git branch: "${params.githubBranch}", url: 'https://github.com/harishRagavendar10/scala_basic.git'
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



