pipeline {
   agent any

   stages{
    stage('CodeScan'){
        steps{
            sh 'trivy fs .  -o result.html'
       
           
        }
    }
    stage('dockerLogin'){
        steps{
            sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 288761730265.dkr.ecr.us-east-1.amazonaws.com'
        }
    }
    stage('dockerImageBuild'){
        steps{
            sh 'docker build -t jenkins-ci .'
            sh 'docker build -t imageversion . '
        }
}
    stage('dockerImageTag'){
        steps{
            sh "docker tag jenkins-ci:latest\
             $IMAGE_ECR_REPO:latest"
            sh "docker tag imageversion \
            $IMAGE_ECR_REPO:v1.$BUILD_NUMBER"
        }    
        }
    
    stage('pushImage'){
        steps{
            sh "docker push \
            $IMAGE_ECR_REPO:latest"
            sh "docker push \
            $IMAGE_ECR_REPO:v1.$BUILD_NUMBER"
        }
    }
   } 
   }