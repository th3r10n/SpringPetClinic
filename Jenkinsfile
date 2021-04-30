pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/th3r10n/SpringPetClinic.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn compile'    
            }
        }
        stage('test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('deploy'){
            steps{
                sh 'java -jar /var/jenkins_home/workspace/PetClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
