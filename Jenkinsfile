pipeline{
  agent any 
  tools {
    maven "maven_3.9.1"
  }  
  stages {
    stage('1GetCode'){
      steps{
        sh "echo 'cloning the latest application version' "
        git credentialsId: 'git-credentials', url: 'https://github.com/DecoTechnologies/webapp.git'
      }
    }
    stage('3Test+Build'){
      steps{
        sh "echo 'running JUnit-test-cases' "
        sh "echo 'testing must passed to create artifacts ' "
        sh "mvn clean package"
      }
    }
  }
}
    /*
    stage('Build') {
      steps {
          withCredentials([
              [$class: 'AmazonWebServicesCredentialsBinding', AWS_ACCESS_KEY_ID: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-creds', AWS_SECRET_ACCESS_KEY: 'AWS_SECRET_ACCESS_KEY']
          ]) {
              sh "echo creating docker image"
              sh "aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 921612666672.dkr.ecr.us-east-2.amazonaws.com"
              sh "docker build -t 921612666672.dkr.ecr.us-east-2.amazonaws.com/webapp-repo:v1 . "
              sh "docker push 921612666672.dkr.ecr.us-east-2.amazonaws.com/webapp-repo:v1"
          }
      }
    }
  }
}
  





    /*
    stage('4CodeQuality'){
      steps{
        sh "echo 'Perfoming CodeQualityAnalysis' "
        sh "mvn sonar:sonar"
      }
    }
  
    stage('5uploadNexus'){
      steps{
        sh "mvn deploy"
      }
    } 
    stage('8deploy2prod'){
      steps{
        deploy adapters: [tomcat8(credentialsId: 'tomcat-credentials', path: '', url: 'http://35.170.249.131:8080/')], contextPath: null, war: 'target/*war'
      }
    }
}
  post{
    always{
      emailext body: '''Hey guys
Please check build status.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    }
    success{
      emailext body: '''Hey guys
Good job build and deployment is successful.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    } 
    failure{
      emailext body: '''Hey guys
Build failed. Please resolve issues.

Thanks
Landmark 
+1 437 215 2483''', recipientProviders: [buildUser(), developers()], subject: 'success', to: 'paypal-team@gmail.com'
    }
  } 
  
}
}
*/
