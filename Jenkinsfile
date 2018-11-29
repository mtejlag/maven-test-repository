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

node {
   checkout scm
   stage('Compilar'){
      
      echo "Comienza la compilacion!!!!"
      /*withMaven(
         maven: 'maven por defecto (3.6.0)'
      ){*/
         
         sh 'mvn compile'
      //}
   }
   stage('Test'){
      
      echo "Comienzan las pruebas!!!!"
   }
   stage('Empaquetar'){
      
      echo "Comienza la empaquetacion!!!!"
   }   
}
