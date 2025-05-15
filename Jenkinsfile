// global variables
// used accroess steps and stages.
// persitant
// Used in the groovy scrpit.   

pipeline{
    agent any

    //environment {
        // Used for shell variables. passing to sh. exists whilst pipeline runs.
        // creds/paths + in builts  
    //}

    //options{
        //timestamps() global
        //disableconcurrentbuilds() global
        //timeout(time: 10, unit: "minutes") global/local
        //retry(5) stage
    //}

    stages{
        stage("Make a directory"){
            options{timeout(time: 1, unit: 'MINUTES')}
            steps{
                //catchError(buildResult:'UNSTABLE' , stageResult:'UNSTABLE'){ 
                sh "mkdir ~/jenkins-dir" // unique sh command - no scripting here!!          
            }
            post{
                success{
                    echo "this was successful"
                }
                failure{
                    echo "failed"
                }
                always{
                    echo "this always prints"
                }
            }
        }
        stage("add file"){
            steps{
                sh "touch ~/jenkins-dir/file1.txt"
            }
        }
    }
}
