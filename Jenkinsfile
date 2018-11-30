/*pipeline {
   agent any
   stages {
      stage('Etapa 1') {
      
         steps {
         
            echo 'Hola mundo'
         }
      }
   }
}*/

pipeline {
   agent any
   stages {
      stage('Compilar') {
      
         steps {
         
            echo 'Comienza la compilacion!!!!'
            withMaven(
               maven: 'maven por defecto (3.6.0)'
            ){
         
               sh 'mvn compile'   
            }
         }
      }
      stage('Test') {
      
         steps {
         
            echo 'Comienzas las pruebas!!!!'
            withMaven(
               maven: 'maven por defecto (3.6.0)'
            ){
         
               sh 'mvn test'   
            }
         }
      }
      stage('Empaquetar') {
      
         steps {
         
            echo 'Comienza la empaquetacion!!!!'
            withMaven(
               maven: 'maven por defecto (3.6.0)'
            ){
         
               sh 'mvn package'   
            }
         }
      }
      
   }
}

/*node {
   checkout scm
   stage('Compilar'){
      
      echo "Comienza la compilacion!!!!"
      withMaven(
         maven: 'maven por defecto (3.6.0)'
      ){
         
         sh 'mvn compile'
      }
   }
   stage('Test'){
      
      echo "Comienzan las pruebas!!!!"
      withMaven(
         maven: 'maven por defecto (3.6.0)'
      ){
         
         sh 'mvn test'
         //junit '***.xml'
      }
   }
   stage('Empaquetar'){
      
      echo "Comienza la empaquetacion!!!!"
      withMaven(
         maven: 'maven por defecto (3.6.0)'
      ){
      try{
         
         sh 'mvn package'
      }finally{
         //deleteDir()
      }
         
      //}
   }   
}*/
