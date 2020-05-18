pipeline {
 agent any
 stages {
  stage('SCM') {
   steps {
    checkout scm
   }
  }
  stage('Dev stage ') {
   parallel {
     stage('Dev Backend ') {
     steps {
      build job: 'backend_pipeline'  
     }
     }
     stage('Dev Frontend '){
     steps {
      build job: 'Frontend'  
     }
     }
     }
     }
    stage('Test stage') {
   parallel {
   stage('Deploy app ') {
     steps {
      sh 'docker-compose -f app.yml up' 
     }
     }
    stage('Test Backend ') {
     steps {
      build job: 'testKatalon' 
     }
     }
    stage('Test Frontend '){
          steps {
    sh 'pwd'
     }
     }
 }
   }
   }
