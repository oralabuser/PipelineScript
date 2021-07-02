pipeline {
	agent none
	stages {
		stage('Non-Parallel Stage') {
			agent {
					label "master"
				}
			steps {
				echo "This stage will be executed first";
			}
		}
		stage('Run Tests') {
			steps {
				echo "Building the checked-out project!";
			}
		}
		stage('Unit-Test') {
			parallel {
				stage('Test on Agent') {
					agent{
						label "AWS_instance_Node"
					}
					steps {
						echo "Task1 on Agent";
					}
				}
				stage('Test On master') {
					agent {
						label "master"
					}
					steps {
						echo "Task1 on Master";
					}
				}
			}
		}
	}
}
