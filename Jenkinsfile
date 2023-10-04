#!/usr/bin/env groovy

@Library('jenkins-shared-library')
def gv

pipeline {
    agent any
    tools {
        maven 'mavan-3.6'
    }
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                    echo "building jar"
                    buildJar()
                }
            }
        }
        stage("build image") {
            steps {
                script {
                    echo "building image"
                    //buildImage()
                    buildImage 'aksxy/java-maven-app:jma-3.0' //passing value in buildImage.groovy for $imageNmae parameter
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    gv.deployApp()
                }
            }
        }
    }   
}
