node {
    stage('Git Checkout') { // for display purposes
     echo 'Checout Code and clone it inside jenkins workspace.'
     git 'https://github.com/padmaavathy/maven_apps.git'
   }
   stage('Build Test & Package') {
      echo 'Build the package'
      sh 'mvn clean compile package'
   }
   stage('SonarQube analysis') {
    withSonarQubeEnv('SonarCloud') {
      // requires SonarQube Scanner for Maven 3.2+
      sh 'mvn clean org.jacoco:jacoco-maven-plugin:prepare-agent package sonar:sonar' +
       '-Dsonar.projectKey=padmavathi:padmavathi' +
       '-Dsonar.login=padmavathi' +
       '-Dsonar.password=efaf4ed9c320f83fb061d004bf7f3addcf38c6f2' +
          //'-Dsonar.language=java ' +
          //'-Dsonar.sources=. ' +
          //'-Dsonar.tests=. ' +
          //'-Dsonar.test.inclusions=**/*Test*/** ' +
          //'-Dsonar.exclusions=**/*Test*/**'   
    }
  }
   stage('Deploy to Dev'){
       echo 'Deploy to Dev environment'
   }
   stage('Deploy to Test'){
       echo 'Deploy to Test environment'
   }
      stage('Test Automation'){
       echo 'Deploy to Dev environment'
   }
   
}
