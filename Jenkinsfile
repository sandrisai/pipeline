pipeline {
    agent {
         label 'app'
    }
       
    stages{
        stage ('git -clone'){
            steps{
               
                git url: 'https://github.com/sandrisai/spring-petclinic.git',
                branch: 'main'
            }
        }
        stage ('build') {
            steps{
                echo 'libries'
                sh 'mvn package'
            }
        }
    }
    post {
        always {
            junit '**/target/surefire-reports/*.xml'
            archiveArtifacts artifacts : '**/target/*.jar'
        }
        success {
             echo 'build successful'
        }
        failure {
            echo 'build failure'
        }

        
    
    }
}

