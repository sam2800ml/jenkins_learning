# Jenkins
Jenkins is a CI/CD tool that helps to automate the software delivery process.

## Software Development life cycle
We need to first identify new features, planning htem, doing the development for those features, after we have to commit the souce code changes, then we build, run and test, and if everything works out those new features are deploy to production

## CI -> Continuos integration
Primarily focuses on automated build and test for every change commited to the version control system by the developers, to be able to implemented we need to make sure that some of the following things works:
- Version control system:
    - Stores all the source code checked by the teams an acts as the single source of truth
- Automated buiold and unit testing:
    - Every commit that makes it to the version control, should be build and text by an independent continuos integration server
- Feedback:
    - Every code commited should have a feedback 
- Agreement on ways of working
    - The way that should be is that every code can be regurlarly commited so it can be tested in each step

## CD -> Continuos Delivery
The continuos integration let you automate the software build and test porcess, and continuos delivery lets you automate the whole applicaiton delivery process, takes any changes in the code and then deploy it.

## Deployment pipelines
They automate all the stages(build, test, release) of your software delivery process.

## Jenkins plugins
Jenkins permit the use of pulgins, this helps to more focus user-needed functionality, such as integrating source code management tools, build tools, reporting tools, code coverage, static analysis.
>
You can install them in the plugins section, theres plenty of options were you can search and then install depending of waht do you need in your project, or if you have your own plugin that you want to use you can manually install it 
you can install new pluggins, unninstall them, update them.

## Jenkins security
Intellectual property (IP) is valuable data and its important to protect it.
- Security features:
    - CSRF Protection: is an attack that forces an end user to execute unwanted actions on a web application in which they are currently authenticated, you can enable the protection to be safe of this attack
    - TCP Port: Jenkins can use a TCP port to communicate with the agents, you can enable a fixed port or you can use a random port 
    - Markup Formatter: you can set up the markuo formatter to plain text by default and that will eliminate any unsafe HTML or javascript
    - Git host key verification: This option uses the git Client plugin, and you can select how to verify the ssh key
    - Authentication: Is yhe process of validating the users, confirming the identity of users, and once the user is authenticated you can determine the actions of the user or the group can perform
        - Anyone can do anything: anonymous and authenticated users can do everything
        - Legacy mode: allows administrators to perform any action, and the rest read-only
        - Logged in users can do anything

## Jenkins Jobs
A jenkins job is a sequential set of tasks that are defined by a user. typical includes retrieving the latest source code from version control, compiling it, running unit test, building and storing the artifacts and notifying the end users of the outcome of the build
Types:
    - Freestyle Project: default type, most flexible to configure
    - pipeline and multibranch: this is the default type and required the installation of plugins to be bale to work
    - Multi-Configuration Project: This is useful for jobs with a large number of configurations, requires matrix project plugins to be installed
Anatomy of the jobs:
    - Configure source code management: you can use the SCM tool of your choice
    - Build trigers: You can schedule periodic building using the cron-like syntax
    - Build after other projects are built: build a job after another dependent job has been built succesfully

>
## Freestyle jobs 
Is the most versatile of all the jenkins job types. it allows you to build any type of project, and it is included in jenkins by default without the need to install aditional plugins

## Pipeline Jobs
Create a set of instructions written as a code to model complex workflows, resume at a certain point on failure, store all pipeline code in SCM
There are two ways of creating pipelines in jenkins, its using the declarative vs scripted pipelines:
- Declarative pipelines: 
    - Provides a richer set of functionality for creating pipelines workflows, they use DSL.
- Scripted pipelines: 
     - 
- Building blocks:
    - Agent: This specifies where the pipeline will run
    - Stages: thi
    - Steps: Is the smallest unit of execution
    - Post: defined additional steps
    - Example: pipeline 
                       ```groovy pipeline {
                    agent any
                    stages {
                        stage('Build') {
                        steps {
                            echo “Run build”
                        }
                        }
                        stage('Test') {
                        steps {
                            echo “Run tests”
                        }
                        }
                    }
                    }```

## Distributed Vuilds Terminology
Terminology
- Controller: Is where the jenkins is installed, stores all the configurations, load plugins.
- Agent: Controls the jenins master and performs various operations as directed by the jenkins Controller
- Node: A machine that can allocate an executor and run jenkins jobs
- Executor: Is a basic bulding block which allows a build to run on a node