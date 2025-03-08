pipeline {
   agent any
   stages{
    stage('clone'){
        steps{
            sh 'echo "clone"'
        }
    }
    stage('test'){
        steps{
            sh 'echo "test"'
            sh 'nproc'
            sh 'pwd'
        }
}
    stage('ceatefile'){
        steps{
            sh 'touch text-$BUILD_ID'
        }
    }
   } 
}