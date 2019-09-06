pipeline{
		agent any
				stages{
			stage('One'){
					steps{
							echo "Hi, THis is Tushar from Panvel"
						 }
			}
		    stage('Two'){
					steps{
						#input('Do you want to proceed?')
						echo "Input option not working"
					     }
			}
			stage('Three'){
					when{
						not{
							 branch "master"
						   }
						}
					steps{
							echo "Hello"
						 }
			}
			stage('Four'){
					parallel{
						stage('Unit Test'){
									steps{
											echo "Running unit test...."
										 }
						}
						stage('Integration Test'){
									agent {
										docker {
											reuseNode true
											image 'ubuntu'
											   }
										  }
										  steps{
												echo "Running Integration Test...."
											   }
						}
					}
			}
			
		}					
}
