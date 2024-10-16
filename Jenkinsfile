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
    }
}