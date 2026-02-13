pipeline {
    
    agent any
    
    stages{
        
         stage('SRINFOETCH POLL SCM Feb release'){
            steps{
                git branch: 'feature/2026.02.06', url: 'https://github.com/srinfotechbatch5/spring-petclinic.git'
            }
        }
        stage('checkout-->clone'){
            steps{
                git branch: 'feature/2026.02.06', url: 'https://github.com/srinfotechbatch5/spring-petclinic.git'
            }
        }
        
        stage('Build'){
            steps{
            bat 'mvn install'
        }
        }
        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }
        stage('Generate Junit Tests Results'){
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('Generated the Artifacts'){
            steps{
                archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
            }
        }
    }
}