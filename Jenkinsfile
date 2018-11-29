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
   stage('Compilar'){
      
      echo "Comienza la compilacion!!!!"
      mvn compile
   }
   stage('Test'){
      
      echo "Comienzan las pruebas!!!!"
   }
   stage('Empaquetar'){
      
      echo "Comienza la empaquetacion!!!!"
   }   
}
