pipeline{
    agent any
    stages{
        stage("NPM Install"){
            steps{
                bat 'npm install'
            }
        }
        stage ('Parallel execution'){
            parallel{
                stage("Audit"){
                    steps{
                        bat 'npm audit'
                    }
                }
                stage("Test"){
                    steps{
                        bat 'npm test'
                    }
                }
            }
        }
        stage("Deploy to Staging"){
            steps{
                input message: 'Deploy to staging', ok: 'Deploy'
            }
        }
        stage("Deploy to Production"){
            steps{
                echo 'Deploy to production'
            }
        }   
    }
}