pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
                           sh '''
				#!bin/bash
				pip install jupyter
				pip install nbconvert
				echo 'Building...'
				jupyter-nbconvert --execute --to=html Jupyter1.ipynb
			      '''
                        }
		}
		stage('Test'){
			steps{
				echo 'Testing..'
			}
		}
	}
}
