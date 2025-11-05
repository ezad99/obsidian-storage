2024-07-02 07:31

Status: #new 

Tags:[[CI/CD]],[[Java]]

# Jenkins
Jenkins is an automation server used to automate various tasks related to build, testing and deploying software.
	Widely used in CI/CD pipelines to facilitate the automated process of integrating code changes, running tests and deploying apps

To define a Jenkins pipeline, we create a Jenkinsfile
```
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yourusername/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deployment steps here
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
        }
        success {
            echo 'Build and tests were successful!'
        }
        failure {
            echo 'Build or tests failed.'
        }
    }
}

```

Explanation
- **Pipeline Block**:
    
    - `pipeline { ... }`: This block defines the pipeline and encloses all its stages and settings.
- **Agent**:
    
    - `agent any`: Specifies that the pipeline can run on any available agent. You can also specify a specific agent or label if needed.
- **Stages**:
    
    - `stages { ... }`: This block contains all the individual stages of the pipeline.
    
    **Checkout Stage**:
    
    - `stage('Checkout') { ... }`: Defines the first stage, typically used for checking out the source code from a version control system.
        - `steps { ... }`: Contains the actual steps to perform within this stage.
        - `git 'https://github.com/yourusername/your-repo.git'`: Checks out the code from the specified Git repository.
    
    **Build Stage**:
    
    - `stage('Build') { ... }`: Defines the build stage where the project is compiled.
        - `sh './gradlew build'`: Runs the Gradle build command.
    
    **Test Stage**:
    
    - `stage('Test') { ... }`: Defines the test stage where tests are executed.
        - `sh './gradlew test'`: Runs the Gradle test command.
    
    **Deploy Stage**:
    
    - `stage('Deploy') { ... }`: Defines the deploy stage where deployment actions are performed.
        - `echo 'Deploying...'`: Placeholder for deployment steps. Replace this with actual deployment commands.
- **Post Block**:
    
    - `post { ... }`: Contains actions that run at the end of the pipeline, depending on the pipeline’s outcome.
    
    **Always Section**:
    
    - `always { ... }`: Steps that run regardless of the build result.
        - `echo 'Cleaning up...'`: Example cleanup step.
    
    **Success Section**:
    
    - `success { ... }`: Steps that run only if the build succeeds.
        - `echo 'Build and tests were successful!'`: Success message.
    
    **Failure Section**:
    
    - `failure { ... }`: Steps that run only if the build fails.
        - `echo 'Build or tests failed.'`: Failure message.