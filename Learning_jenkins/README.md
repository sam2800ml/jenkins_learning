# Learning Jenkins

In this repository will be uploaded everything that i learn about how to use jenkins, and after do an implementation with machine learning

## Pipeline
is a suite of pluggins which support implementing and integrating continuos delivery pipelines into jenkins.

A continuous delivery pipeline is an automated expression of your process for getting software version control

Theres two way of defining a pipeline:
- Declarative pipeline
- Scripted pipeline -> is written in a limited form of Groovy syntax

Jenkinsfile {Declarative pipeline}

In the following pipeline wil be creating a pipeline that in the stage 1 its going to be printing Hello world 
```
pipeline { // This is the pipeline creation
    agent any // Instruct jenkins to allocate an executor, for the entire pipeline
    stages { // Its whats happening in the moment of the creation
        stage('Stage 1') {
            steps {
                echo 'Hello world!'
            }
        }
    }
}
```

This is going to be one way of doing it, but we can also do a in SCM, this way its going to be working by using a git repository where the jenkinsfile its going to be created 