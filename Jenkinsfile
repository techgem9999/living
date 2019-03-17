pipeline{
agent any
stages{
stage('check out'){
steps{
   checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/techgem9999/living.git']]])
   }}
   stage('compile'){
   steps{
      sh '/opt/apache-maven-3.6.0/bin/mvn compile'
   }}
   stage('test'){
   steps{
      sh '/opt/apache-maven-3.6.0/bin/mvn test'
   }}
   stage('package the application'){
   steps{
      sh '/opt/apache-maven-3.6.0/bin/mvn package'
   }}
   stage('archive artifacts'){
   steps{
      archiveArtifacts ''
   }}
}}
