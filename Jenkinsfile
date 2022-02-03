pipeline {

agent any

stages{

stage('code-checkout'){
    steps{
    
    checkout([
                    $class: 'GitSCM',
                    branches: [[name: "main"]],
                    doGenerateSubmoduleConfigurations: false,
                    extensions: [[$class: 'CleanBeforeCheckout'], [$class: 'CloneOption', depth: 1, shallow: true, timeout: 240], [$class: 'CheckoutOption', timeout: 100]],
                    submoduleCfg: [],
                    userRemoteConfigs: [[url: 'https://github.com/prithvi1125/Demo.git']]
                ])
    }}

stage('eksdeploy') {
    steps{
     withKubeCredentials([
     [clusterName: 'demo', contextName: "iam-root-account@demo.ap-south-1.eksctl.io", credentialsId: "demo", namespace: "default", serverUrl: "https://B5C23D146B890FA2B2902007A75878F1.sk1.ap-south-1.eks.amazonaws.com"]
      ])
     {
     script {
     sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'  
        sh 'chmod u+x ./kubectl'  
         sh  """kubectl  get po """
}}}}


}}


  
