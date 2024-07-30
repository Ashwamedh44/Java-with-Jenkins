pipeline{
    agent any
    
    stages{
        stage ("compile"){
            bat 'javac Main.java'
        }
        stage ("run"){
            bat 'java Main.java'
        }
    }
}