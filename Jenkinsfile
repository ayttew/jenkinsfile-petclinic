node {
   stage 'Checkout'
   git url: 'https://github.com/spring-projects/spring-petclinic.git'
   def mvnHome = tool 'mvn'
   
   try {
    stage 'Build'
    sh "${mvnHome}/bin/mvn clean install"
   
    stage 'Archive'
    archive 'target/petclinic.war'
   } catch (err) {
    emailext body: 'Hi, your build successfully failed', subject: 'Test jenkins', to: 'rudakovaa@sgu.ru'
   }
}
