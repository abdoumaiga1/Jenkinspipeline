pipeline {
   agent any
   stages{
    stage('Codescsn'){
        steps{
            sh 'trivy --version'
        }
    }
    stage('dockerImageBuild'){
        steps{
            sh 'docker -v'
        }
}
    stage('pushIamge'){
        steps{
            sh 'touch text-$BUILD_ID'
        }
    }
   } 
}