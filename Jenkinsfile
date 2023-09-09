pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "building"
                mvn clean package
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
            steps{
                 echo "Completed"
            }
        }
    }
}
