pipeline{
    agent any
    environment {
        DIRECTORY_PATH= "/Users/benbradhurst1/Documents/Deakin/2023/Trimester 2/SIT753 Professional Practice in It/Week 5/Jenkins"
        TESTING_ENVIRONMENT= "Mocha"
        PRODUCTION_ENVIRONMENT= "AWS EC2"
    }
    stages{

        stage('Build'){
            steps{
                echo "Fetch the source code from the directory path $DIRECTORY_PATH"
                echo "compile and build code using Maven"
		sleep(2)
		echo "Build complete"
            }
		}
        stage('Test'){
            steps{
                echo "Running unit tests in $TESTING_ENVIRONMENT"
		sleep(2)
		echo "Unit tests completed"
                echo "running Integration Tests in $TESTING_ENVIRONMENT"
		sleep(2)
		echo "Integration Tests completed
            }
	    post{
		always{
		    mail to :"benbradhurst@gmail.com",
		    subject: "Test Status Email",
		    body: "Test Successful, ${BUILD_LOG, maxLines, escapeHtml}"
		}
	    }
        
        
        stage('Code Quality Check'){
            steps{
                echo "Running quality tests via Checkstyle"
		sleep(5)
		echo "Quality check complete"

            }
        }
    	stage('Security Check'){
    		steps{
			echo "Running Snyk Security scan..."
			sleep(5)
			echo "No vulnerabilities found"

    		}
		post{
			always{
			    mail to :"benbradhurst@gmail.com",
			    subject: "Security Check Status Email",
			    body: "Security Check passed, ${BUILD_LOG, maxLines, escapeHtml}"
			}
	        }
        }
		stage('Deployment to Staging Environment')
	      	steps{
			echo "Deploying to  $PRODUCTION_ENVIRONMENT"
			sleep(1)
			echo "Deployment successful"
	      }
	
    	stage('Integrated Staging Tests'){
            steps{
                echo "Running integrated staging tests with Jasmine"
			sleep(3)
			echo "Integrated staging tests complete"

            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deployed to $PRODUCTION_ENVIRONMENT"

            }
        }
    
}
