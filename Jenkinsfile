pipeline{
    agent any
    environment {
        DIRECTORY_PATH= "/Users/benbradhurst1/Documents/Deakin/2023/Trimester 2/SIT753 Professional Practice in It/Week 5/Jenkins"
        TESTING_ENVIRONMENT= "Mocha"
        PRODUCTION_ENVIRONMENT= "Ben"
    }
    stages{
    	stage('Preparation') {
	    	steps {
	        	cleanWs()
	    	}
	}
        stage('Build'){
            steps{
                echo "Fetch the source code from the directory path $DIRECTORY_PATH"
                echo "compile code and generate any necessary artifacts"
		mvn -version
            }
	post{
                always{
                    mail to :"benbradhurst@gmail.com",
                    subject: "Build Status Email",
                    body: "Build log attached!"
                }
            }
        }
        stage('Test'){
            steps{
                echo "Unit Tests completed"
                echo "Integration Tests completed"
            }
        }
        stage('Code Quality Check'){
            steps{
                echo "Checked the quality of the code"

            }
        }
        stage('Deploy'){
            steps{
                echo "deploy the application to the testing environment $TESTING_ENVIRONMENT"

            }
        }
        stage('Approval'){
            steps{
                sleep(10)
                echo "Approval started and completed!"

            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deployed to $PRODUCTION_ENVIRONMENT"

            }
        }
    }
}
