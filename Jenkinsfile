pipeline{
    agent any
    stages{
        stage ("cloning") {
            steps{
                git url:"https://github.com/sudarshan0718/new_repo.git" , branch: "main"

            }
        }
        stage ("dependency") {
            steps{
                bat '''
                    python -m venv venv
                    call venv\\Scripts\\activate
                    python -m pip install --upgrade pip
                    pip install pytest
                '''
            }
        }
        stage ("testing"){
            steps{
                bat '''
                    call venv\\Scripts\\activate
                    pytest test.py
                '''

            }
        }
        stage ("deploy"){
            bat '''
                call venv\\Scripts\\activate
                python adding.py
            '''

        }
        
    }
}