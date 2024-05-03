pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "== BUILDING =="
                echo "Build the code using a build automation tool, such as Grunt, Apache Ant, or Gradle, to compile and package the code"
            }
        }
        stage('Unit and Intgration Test') {
            steps {
                sh 'mvn clean install 2>&1 | tee stage_logs.txt'
                echo "== UNIT AND INTEGRATION TESTING =="
                echo "Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected, using a test automation tool like Appium, Cypress, or Ketalon"
            }
            post{
                success{
                    emailext to: "zozo.edge7@gmail.com",
                    subject: "Build Status Email",
                    body: "Pipeline stage completed successfully!",
                    attachLog: true,
                    attachmentsPattern: 'stage_logs.txt'
                }
                failure{
                    emailext to: "zozo.edge7@gmail.com",
                    subject: "Build Status Email",
                    body: "Pipeline stage failed this stage",
                    attachLog: true,
                    attachmentsPattern: 'stage_logs.txt'
                    }
                }
          }
        stage('Code Analysis') {
            steps {
                echo "== CODE ANALYSIS =="
                echo "Integrate a code analysis tool, like Clang, Visual Assist, or CodeScene, to analyse the code and ensure it meets industry standards"
            }
        }
        stage('Security Scan') {
            steps {
                sh 'mvn clean install 2>&1 | tee stage_logs.txt'
                echo "== SECURITY SCANNING =="
                echo "Perform a security scan on the code using a tool, like AppScan, SonarQube, or Veracode, to identify any vulnerabilities"
            }
            post{
                success{
                    emailext to: "zozo.edge7@gmail.com",
                    subject: "Build Status Email",
                    body: "Pipeline stage completed successfully!",
                    attachLog: true,
                    attachmentsPattern: 'stage_logs.txt'
                }
                failure{
                    emailext to: "zozo.edge7@gmail.com",
                    subject: "Build Status Email",
                    body: "Pipeline stage failed this stage",
                    attachLog: true,
                    attachmentsPattern: 'stage_logs.txt'
                    }
                }
          }
        stage('Integration Tests on Staging') {
            steps {
                sh 'mvn clean install 2>&1 | tee stage_logs.txt'
                echo "== INTEGRATION TESTING ON STAGING =="
                echo "Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment"
            }
            post{
                success{
                    emailext to: "zozo.edge7@gmail.com",
                    subject: "Build Status Email",
                    body: "Pipeline stage completed successfully!",
                    attachLog: true,
                    attachmentsPattern: 'stage_logs.txt'
                }
                failure{
                    emailext to: "zozo.edge7@gmail.com",
                    subject: "Build Status Email",
                    body: "Pipeline stage failed this stage",
                    attachLog: true,
                    attachmentsPattern: 'stage_logs.txt'
                    }
                }
          }
        stage('Deploy to Production') {
            steps {
                echo "== DEPLOYMENT TO PRODUCTION =="
                echo "Deploy the application to a production server"
            }
        }
    }
}
