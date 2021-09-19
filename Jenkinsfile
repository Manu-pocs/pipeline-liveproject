pipeline {
    agent any

    stages {
        stage('Setup & Verify') {
            steps {
                echo 'Setting up Env and Verification'
            }
        }
        stage('Lint Analysis') {
            steps {
                echo 'Code Quality checks using Lint'
            }
        }
        stage('Unit Tests') {
            steps {
                echo 'Execute Unit Tests'
            }
        }
        stage('Build') {
            steps {
                echo 'Build Automation'
            }
        }
	stage('Parallel Stages-Tests') {
		when {
			branch 'master'
		}
		parallel {		
			stage('E2E Tests') {
				steps {
					echo 'Execute Unit Tests'
				}
			}
			stage('Load Tests') {
				steps {
					echo 'Execute Load Tests'
				}
			}
			stage('Security Tests') {
				steps {
					echo 'Execute Security Tests'
				}
			}			
		}
	}
        stage('Build & Push Images') {
            steps {
                echo 'Build & Push Docker Images to Registry'
            }
        }
        stage('TF Plan') {
            steps {
                echo 'Create Terraform Plan'
            }
        }	
        stage('TF Apply') {
            steps {
                echo 'Create Resources in Cloud'
            }
        }		
        stage('Deploy to Cluster') {
            steps {
                echo 'Execute Unit Tests'
            }
        }
    }
}
