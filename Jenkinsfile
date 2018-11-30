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

/*pipeline {
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
   post{
         
      always{
            
         deleteDir()
      }
      failure{
         echo "UPSSS!!"
      }
      success{
            
         echo "Exito"
      }
      changed{
            
         echo "cambio"
      }
   }         
}*/

/*node {
    try {
        stage('Test') {
            sh 'echo "Exito!"; exit 0'
        }
        echo 'Se ejecuta si exito'
    } catch (e) {
        echo 'Se ejecuta si fallo'
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'SUCCESS'
        if (currentResult == 'UNSTABLE') {
            echo 'Se ejecuta si unstable'
        }

        def previousResult = currentBuild.previousBuild?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'Se ejecuta si hay cambio de estado'
        }

        echo 'Se ejecuta siempre'
    }
}*/

node (master){
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
         //junit '*\/**.xml'esto es necesario si no se usa pluging withMaven para ver los resultados de los test
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
            deleteDir()
         }         
      }
   }   
}
