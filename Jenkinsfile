incomplete


pipeline {
    agent none
    stages {
        stage('npm commands') {
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                sh 'dotnet build'
                sh 'npm install'
                sh 'npm run build'
                sh 'dotnet test'
            }
        }
        stage('Dot Net Commands') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}


    - name: Build the C#       # Name of step
      run: dotnet build        # Command to run
  
    - name: Build the TypeScript code 1.      # Name of step
      working-directory: DotnetTemplate.Web
      run:  npm install        # Command to run

    - name: Build the TypeScript code 2.      # Name of step
      working-directory: DotnetTemplate.Web
      run:  npm run build        # Command to run

    - name: Run the C# Tests   # Name of step
      run: dotnet test         # Command to run

    - name: run the TypeScript tests  # Name of step
      working-directory: DotnetTemplate.Web
      run: npm t               # Command to run
      
    - name: un linting on the TypeScript code   # Name of step
      working-directory: DotnetTemplate.Web
      run: npm run lint         # Command to run
