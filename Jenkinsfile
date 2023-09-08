pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "building"
            }
            post{
                always{
                    mail to :"benbradhurst@gmail.com",
                    subject: "Build Status Email",
                    body: "Build log attached!"
                }
            }
        }
        stage("Test"){
            steps{
                echo "Testing..."
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploying..."
            }
        }
        stage("Complete"){
              echo "Completed"
        }
    }
}
