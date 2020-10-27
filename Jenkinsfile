def artifactname = "sp-boot-app.jar"
def repoName = "sp-boot-app-repo"
def pipelineName = "devops_vk_pipeline"
def semanticVersion = "${env.BUILD_NUMBER}.0.0"
def packageName = "spboot-package_${env.BUILD_NUMBER}"
def version = "${env.BUILD_NUMBER}.0"
def buildNumber = "${env.BUILD_NUMBER}"
/////def orchToolId="1153dbd753f100107109ddeeff7b122e"  
//${env.BUILD_NUMBER}
pipeline {
	agent any
	tools {
		maven 'Maven'
	}
	stages {
		stage("checkout") {
		stages {
			stage('deploy to dev') {
				when {
					branch 'dev'
				}
				steps {
					echo "Building in UAT"
				}
			}
			stage('deploy to prod') {
				when {
					branch 'master'
				}
				steps {
					echo "Building in prod"
				}
			}
		}
	}

	stage("build") {
		stages {
			stage('deploy to dev') {
				when {
					branch 'dev'
				}
				steps {
					echo "Manual Building in UAT"
				}
			}
			stage('deploy to prod') {
				when {
					branch 'master'
				}
				steps {
					echo "Manual Building in prod"
				}
			}
		}
     }

	stage('unit-tests') {
		stages {
			stage('deploy to dev') {
				when {
					branch 'dev'
				}
				steps {
					echo "Manual Test in UAT"
				}
			}
			stage('deploy to prod') {
				when {
					branch 'master'
				}
				steps {
					echo "Manual Test in prod"
					writeFile file: 'testng-results.xml', text: '{"name":"com.slokam.automation.opencart.testscripts - 55","passedTests":4,"failedTests":0,"skippedTests":0,"blockedTests":0,"totalTests":4,"startTime":"2020-10-27T04:20:30.124Z","finishTime":"2020-10-27T04:20:30.137Z","duration":0.013,"buildNumber":"${buildNumber}","stageName":"Tests","pipelineName":"ScriptedPipelineVK","passingPercent":100,"url":"http://MSJC7FBCA825.local:3000/jenkins/job/ScriptedPipelineVK/${buildNumber}/testReport/com.slokam.automation.opencart.testscripts","branch":"","isMultiBranch":"false"}'

				}
			}
		}
	}

	stage("deploy") {
		stages {
			stage('deploy to dev') {
				when {
					branch 'dev'
				}
				steps {
					echo "deploy in UAT"
				}
			}
			stage('deploy to prod') {
				when {
					branch 'master'
				}
				steps {
					echo "deploy in prod"
					snDevOpsChange()
				}
			}
		}
	}

}
}
