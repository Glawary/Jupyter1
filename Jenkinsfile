pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
				echo 'Building...'
				jupyter-nbconvert --execute --to=html ./Jupyter1.ipynb
			}
		}
		stage('Test'){
			steps{
				echo 'Testing..'
			}
		}
	}
}
