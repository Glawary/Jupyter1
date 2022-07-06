pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
				echo 'Building...'
				touch run.sh
				echo 'jupyter-nbconvert --execute --to=html Jupyter1.ipynb' > run.sh
                                chmod +x run.sh
				./run.sh
			}
		}
		stage('Test'){
			steps{
				echo 'Testing..'
			}
		}
	}
}
