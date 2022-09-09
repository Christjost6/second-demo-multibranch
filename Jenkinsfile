pipeline{
	agent any 
	stages{
		stage('git clone'){
		   checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/Christjost6/second-demo-multibranch.git']]])
			steps{
				
			}
		}
		stage('parallel-level1'){
			parallel {
				stage('sub-job1'){
					steps{
						echo "sub-job1 task"
					}
				}
				stage('sub-job2'){
					steps{
						echo "sub-job2 task"
						echo "testing second demo"
					}
				}
			}
		}
		stage('version-check'){
			steps{
				echo "end of parallel job"
			}
		}
	}
}
