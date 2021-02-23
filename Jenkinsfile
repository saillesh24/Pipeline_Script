pipeline {
	agent none
	stages {
		stage('Non-Parallel Stage') {
			agent {
				label "master"
			}
			steps {
				echo 'This stage will be executed first'
			}
		}
		stage('Run Tests') {
			parallel {
				stage('Test on Agent1') {
					agent {
						label "Agent1"
					}
					steps {
						echo "Tasks on agent1"
					}
				}
				stage('Test on Agent2') {
				    agent {
				        label 'Agent2'
				    }
				    steps {
				        echo "Test on Agent2"
				    }
				}
			}
		}
		stage('Test on Master') {
			agent {
				label "master"
			}
			steps {
				echo "Tasks on master"
			}
		}
	}
}
