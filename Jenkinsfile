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
                ))))
  
