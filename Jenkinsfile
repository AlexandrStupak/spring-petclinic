pipeline {
    agent any
	environment {
		DOCKER_HUB_USER = 'alexandrstupak0112'
		DOCKER_HUB_REP = 'spring-petclinic'
		DOCKER_HUB_VERSION = '2.6.0-SNAPSHOT'
		JAR_PROJECT_NAME = 'spring-petclinic'
	}
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				script {
					docker.build("${DOCKER_HUB_USER}/${DOCKER_HUB_REP}:${DOCKER_HUB_VERSION}", "--build-arg JAR_VERSION=${DOCKER_HUB_VERSION} —build-arg JAR_ARTIFACT_ID=${JAR_PROJECT_NAME} -f Dockerfile .")
				}
				echo 'Building is done'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}