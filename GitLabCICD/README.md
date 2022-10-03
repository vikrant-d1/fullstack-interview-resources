#                                                                GitLab CI/CD

# Interview-questions

### 1. What is CI/CD in GitHub?

The software development process called continuous integration (CI) involves the automated building, testing, and integration of code changes within a shared repository. Similarly, continuous delivery or deployment involves automatically delivering code changes to production-ready environments or directly deploying code changes to customers.

### 2. How does GitLab CI work?

Continuous integration (CI) begins with your GitLab instance. You can share new code via merge requests, and you can initiate a pipeline of automated processes. The build, test, and deploy pipelines will run after code is committed to the repository. Continuous delivery (CD) allows you to take your project from concept to completion. It does this by putting your features into production after automated pipelines have been validated through CI.

### 3. Is GitHub the same as GitLab?

Because both GitHub and GitLab are version control systems, it can be difficult to choose one of the two. The most significant difference between the two is that GitHub primarily focuses on collaboration and code review, whereas GitLab focuses on DevOps as well as continuous integration and continuous delivery (CI/CD).

### 4. Could you tell me the requirements for CI-CD?

Continuous integration (CI) requires developers to merge their changes to the main code branch many times per day. Each code merges trigger an automated build and test sequence so that developers can quickly detect problems early on in the software development lifecycle.


### 5. What are CI/CD pipeline stages?

There are four stages of a CI/CD pipeline: 

- Source Stage
- Build Stage
- Test Stage
- Deploy Stage


### 6. Could you explain how does a CI CD pipeline works?

A continuous integration/continuous delivery pipeline automates the software delivery process. The pipeline builds code, runs tests, and safely deploys a new version of the application. Automated pipelines remove manual errors, provide standardized feedback loops to developers, and enable fast product iterations.

### 7. How do you manage a CI/CD pipeline?

The main principles of CI are that you:

- Check-in code infrequently.
- Automate the build and test portion.
- Always test the code locally before checking it in.
- Never merge any failed branches to the main branch.
- Return its status back to successful if you’re the developer who causes the failed build or test


### 8. What is the function of the CI system?

The objective of CI is to establish a dependable system for building, packaging, and testing software. This consistency provides an efficient environment for frequent code changes and collaboration, which leads to better software quality.

### 9. Could you explain the working of the GitLab CD?

GitLab CI/CD integrates seamlessly into an existing development workflow. You can set up a project by discussing a feature implementation in an issue and working locally on the proposed change, then pushing commits to a feature branch in a remote repository that’s hosted in GitLab. When you push your commits to the feature branch, the CI/CD pipeline for the project is triggered.

### 10. How would you set environment variables in GitLab CI?

When using variables there is no need to hard code values. In GitLab, CI/CD variables can be defined by going to Settings » CI/CD » Variables, or by simply defining them in the.gitlab-ci.yml file

### 11. How do you use variables in the GitLab pipeline?

GitLab variables can be used to pre-define the values. Go to your project page, Settings tab -> CI/CD, find Variables and click on the Expand button. Here you can define variable names and values, which will be automatically passed into the GitLab pipelines, and are available as environment variables there.

### 12. What is deployment in testing?

The deployment of new applications and modules, updates, and patches from developers to users depends on the methods used by developers to build, test, and deploy code. The speed with which a product responds to customer preferences or requirements depends on these methods. Deployment methods can also impact the quality of code changes.

### 13. Could you explain the process of deployment?

The deployment process flow consists of 5 steps: 

- Planning
- Development
- Testing
- Deploying
- Monitoring


### 14. What is the difference between build and deploy?

Build and deploy are testing terms with important meanings in the IT field. “Build” means consolidating and combining a set of executable code for testing. “Deploy” means injecting that set of executable code into a particular software environment to test it.

### 15. How would you define the GitLab workflow?

The Flow process incorporates a pre-prod branch to fix bugs before merging changes back to main (typically from dev) before going to production. Each team can have as many pre-prod branches as needed — for example, from main to test, from test to acceptance, and from acceptance to production.

### 16. Can you elaborate on the release flow?

Flow is a trunk-based development approach in which the master branch is deployed and developed. Branches are created off the master branch when there are special needs, but the branches do not serve as deployment targets. Here a pull request merges a branch back into the master branch.

### 17. What is the most important deployment step?

Systematic communication is an important element of deployment management. Without communication, many problems can arise, including scheduling conflicts and misunderstandings about the scope of a deployment. Post-deployment check-ins with decision-makers can help your team arrive at timely and accurate decisions, allowing you to avoid many common deployment issues.

### 18. What are artifacts in GitLab CI?

In GitLab 12.4, files and directories from internal and private projects can be previewed when access control is enabled using GitLab Pages. Jobs can output an archive of all the files and directories that are generated as part of the job run in a .zip file. This output is known as a job artifact, which can be downloaded using the GitLab UI or API.

### 19. Could you explain what are deployment artifacts?

A deployment artifact, also known as an “archive file,” is the file generated by a build that contains all the information required to deploy the application to runtime. This type of file is created in the design phase and then handed off to the run-time environment.

### 20. Where are artifacts stored in GitLab CI?

The artifacts are stored in /home/git/gitlab/shared/artifacts by default. In order to keep them backed up regularly, you should save the file and restart GitLab.

### 21. What is cache dependency?

Cache dependencies enable the system to expire cached items when related objects are modified automatically. The system uses dummy cache keys, or cache items with no data that represent one or more other objects, to create dependencies between cached data and other objects.

### 22. What do you know about the dependency proxy?

GitLab provides a local cache called the Dependency Proxy for frequently-accessed upstream images. The Dependency Proxy can act as a pull-through cache in the case of CI/CD by receiving a request from your build server and returning the requested image from the registry.

### 23. How would you explain Docker layer caching?

 Docker Layer Caching (DLC) is a useful feature to enable during continuous integration and continuous delivery (CI/CD) jobs in order to create reusable images that do not change each time they are run. Docker Layer Caching (DLC) is a feature that helps reduce the time it takes to run your containers by keeping track of changes to images so that they do not have to be rebuilt every time you upgrade your container.

### 24. How does GitLab caching work?

A cache is a set of files that a job can download before the execution, and upload after completion. The default location of the cache is the home directory of the GitLab Runner. If the distributed cache is configured, S3 works as storage. After execution, it will upload the cache back to the S3 bucket (push).

### 25. What is a GitLab registry?

GitLab Container Registry is a secure and private registry for Docker images. Built on open-source software and tightly integrated with GitLab, Container Registry gives every user—from solo developers to large enterprise—a single, secure interface to manage their projects, as well as all their containerized applications and services.

### 26. Read git lab documentation for konw more about configration CI/CD in your Porject.
[Git Lab yml File configrations](https://docs.gitlab.com/ee/ci/yaml/index.html "YML File")


### 27. GitLab Runners
- An application that works with GitLab CI/CD to pick and execute CI/CD jobs.
- Open-source and written in Go Language.
- You can add or remove runners into your GitLab architecture.
- GitLab offers serveral shared runners available to every project in a GitLab instance.
- GitLab Runner application can be installed on infrastructure that you own or manage.
- Should install GitLab Runner on a machine seprate from the one that hosts GitLab instance.
- Runner can be installed on an operating system that can compile a Go binary.
- Runner are created by Administrator and are visible in the GitLab UI.
- GitLab Runner should be of the some version individual runners.
- After apprication installation, register individual runners.
- When you register a runner, you must choose an executor.


### 28.Global keywords that configure pipeline behavior:
- default:	Custom default values for job keywords.
- include:	Import configuration from other YAML files.
- stages:	The names and order of the pipeline stages.
- variables:	Define CI/CD variables for all job in the pipeline.
- workflow:	Control what types of pipeline run.

### 29.Jobs configured with job keywords:
- after_script:	Override a set of commands that are executed after job.
- allow_failure:	Allow job to fail. A failed job does not cause the pipeline to fail.
- artifacts:	List of files and directories to attach to a job on success.
- before_script:	Override a set of commands that are executed before job.
- cache:	List of files that should be cached between subsequent runs.
- coverage:	Code coverage settings for a given job.
- dast_configuration:	Use configuration from DAST profiles on a job level.
- dependencies:	Restrict which artifacts are passed to a specific job by providing a list of jobs to fetch artifacts from.
- environment:	Name of an environment to which the job deploys.
- except:	Control when jobs are not created.
- extends:	Configuration entries that this job inherits from.
- image:	Use Docker images.
- inherit:	Select which global defaults all jobs inherit.
- interruptible:	Defines if a job can be canceled when made redundant by a newer run.
- needs:	Execute jobs earlier than the stage ordering.
- only:	Control when jobs are created.
- pages:	Upload the result of a job to use with GitLab Pages.
- parallel:	How many instances of a job should be run in parallel.
- release:	Instructs the runner to generate a release object.
- resource_group:	Limit job concurrency.
- retry:	When and how many times a job can be auto-retried in case of a failure.
- rules:	List of conditions to evaluate and determine selected attributes of a job, and whether or not it’s created.
- script:	Shell script that is executed by a runner.
- secrets:	The CI/CD secrets the job needs.
- services:	Use Docker services images.
- stage:	Defines a job stage.
- tags:	List of tags that are used to select a runner.
- timeout:	Define a custom job-level timeout that takes precedence over the project-wide setting.
- trigger:	Defines a downstream pipeline trigger.
- variables:	Define job variables on a job level.
- when:	When to run job.


### 30. What is version control?

Version control is a set of practices and tools for managing codebases. Developers use version control to keep track of every line of code, and share, review, and synchronize changes among a team.
### 31. What is Git?

Created by Linus Torvalds to support the open-source development of Linux, Git is the most popular version control tool. It uses a distributed repository model that can efficiently handle projects of any size.
### 32. What is a Git repository?

A Git repository keeps track of every file in a software project. The repository serves as an index for all files and changes in the project, allowing developers to navigate to any point in the project’s history.
### 33. Which other version control tools do you know of?

- Mercurial
- Subversion (SVN)
- Concurrent Version Systems (CVS)
- Perforce
- Bazaar
- Bitkeeper
- Fossil

### 34. What is a Git branch?

A Git branch is an independent line of development, usually created for working on a feature. Branches let developers code without affecting the work of other team members.
### 35. What is merging?

Merging consists of joining branches. For example, when developers incorporate their peer-reviewed changes from a feature branch into the main branch.
### 36. What is trunk-based development?

Trunk-based development is a branching model where most of the work takes place in a single trunk, usually called trunk, master, or main. The trunk receives daily merges from all developers in the team.

Trunk-based development is a popular development model because it simplifies version control. Since the trunk is a single source of truth, this model minimizes the chances of merge conflict.
### 37. What is Gitflow, and how does it compare to trunk-based development?

Gitflow is a workflow for Git that makes heavy use of branches. In Gitflow, all the code is merged into the develop branch instead of the main branch, which serves as an abridged version of the project’s history.

Features are worked on specific “feature branches” (typically prefixed with feature/). In the same fashion, releases also create a dedicated release/ branch.

Compared with trunk-based development, Gitflow is more complex and has a higher chance of inducing merge conflicts, which is why it has fallen out of favor among the development community.
### 38. How long should a branch live?

In the context of continuous integration, branches should follow trunk-based development practices and thus be short-lived. Ideally, a branch should last for a few hours or, at most, a day.
CI/CD

Your CI/CD interview questions will, at the minimum, cover some basic concepts such as what is CI and how it works.
### 39. What is continuous integration?

Continuous Integration (CI) is a software development methodology where developers — following the trunk-based model — merge their changes to the main branch many times per day.

CI is supported by automated tests and a build server that runs them on every change. As a result, failures are made visible as soon as they are introduced and can be fixed within minutes.
### 40. How do CI and version control relate to one another?

Every change in the code must trigger a continuous integration process. This means that a CI system must be connected with a Git repository to detect when changes are pushed, so tests can be run on the latest revision.
### 41. What’s the difference between continuous integration, continuous delivery, and continuous deployment?

Continuous integration (CI) executes the sequence of steps required to build and test the project. CI runs automatically on every change committed to a shared repository, offering developers quick feedback about the project’s state.

Continuous delivery is an extension of CI. Its goal is to automate every step required to package and release a piece of software. The output of a continuous delivery pipeline takes the form of a deployable binary, package, or container.

Continuous deployment is an optional step-up from continuous delivery. It is a process that takes the output from the delivery pipeline and deploys it to the production system in a safe and automated way.
A CI/CD workflowA complete CI/CD workflow
### 42. Name some benefits of CI/CD

- Less risk: automated tests reduce the chance of introducing bugs, creating a safety net that increases the developer’s confidence in their code.
- More frequent releases: the automation provided by continuous delivery and continuous deployment allows developers to release and deploy software safely many times per day.
- Improved productivity: freed from the manual labor of building and testing the code, developers can focus on the creative aspects of coding.
- Elevated quality: CI acts as a quality gate, preventing code that is not up to standards from getting released.
- Better design: the iterative nature of continuous integration lets developers work in small increments, allowing a higher degree of experimentation, which leads to more innovative ideas.

### 43. What are the most important characteristics in a CI/CD platform?

- Reliability: the team depends on the CI server for testing and deployment, so it must be reliable. An unreliable CI/CD platform can block all development work.
- Speed: the platform should be fast and scalable to obtain results in a few minutes.
- Reproducibility: the same code should always yield the same results.
- Ease of use: easy to configure, operate, and troubleshoot.

### 44. What is the build stage?

The build stage is responsible for building the binary, container, or executable program for the project. This stage validates that the application is buildable and provides a testable artifact.
### 45. What’s the difference between a hosted and a cloud-based CI/CD platform?

A hosted CI server must be managed like any other server. It must be first installed, configured, and maintained. Upgrades and patches must be applied to keep the server secure. Finally, failures in the CI server can block development and stop deployments.

On the other hand, a cloud-based CI platform does not need maintenance. There’s nothing to install or configure, so organizations can immediately start using them. The cloud provides all the machine power needed, so scalability is not a problem. Finally, the reliability of the platform is guaranteed by SLA.
### 46. How long should a build take?

Developers should get results from their CI pipeline in less than 10 minutes. That’s the longest time that’s practical to wait for results.
### 47. Is security important in CI/CD? What mechanisms are there to secure it?

Yes. CI/CD platforms have access to all kinds of sensitive data such as API keys, private repositories, databases, and server passwords. An improperly secured CI/CD system is a prime target for attacks and can be exploited to release compromised software or to get unauthorized access. A CI/CD platform must support mechanisms to securely manage secrets, and control access to logs and private repositories.
### 48. Can you name some deployment strategies?

- Regular release/deployment: releases software to everyone at once, making it available to the general public.
- Canary releases: this is a method that reduces the chance of failure by exposing a small portion of the userbase (around 1%) to the release. With a canary release, developers gradually switch users to the latest release in a controlled way.
- Blue-green releases: consists of running two simultaneous instances of an application; one is the stable version currently serving users and the other the latest release. Users are switched from the former to the latter all at once. This method is safer than the regular or big bang releases because users can instantly be routed back to the previous version if there is a problem.
- Dark launches: are deployments where new features are released without being announced. Features can be enabled in a very fine-grained way with feature flags.


### 49. How does testing fit into CI?

Testing is integral to and inseparable from CI. The main benefit teams get from CI is continuous feedback. Developers set up tests in the CI to check that their code behaves according to expectations. There would be no feedback loop to determine if the application is in a releasable state without testing.
### 50. Should testing always be automated?

Yes, CI requires that all tests are automated. They must work without human intervention.

That is not to say that manual or exploratory testing don’t have their places. They are very useful for discovering potential features and finding further test cases to automate.
### 51. Name a few types of tests used in software development

There are more types of tests than we can count with both hands, but the most common ones are:

- Unit tests: validate that functions or classes behave as expected.
- Integration tests: are used to verify that the different components of an application work well together.
- End-to-end tests: check an application by simulating user interaction.
- Static tests: finds defects in code without actually executing it.
- Security tests: scans the application’s dependencies for known security issues.
- Smoke tests: fast tests that check if the application can start and that the infrastructure is ready to accept deployments.

### 52. How many tests should a project have?

There is no single answer as it depends on the size and nature of the project. That being said, for various reasons, test suites tend to follow in distribution the testing pyramid.
The testing pyramid may be part of your CI/CD interview questions.The testing pyramid
### 53. What is a flaky test?

A test that intermittently fails for no apparent reason is called a flaky test. Flaky tests usually work correctly on the developer’s machine but fail on the CI server. Flaky tests are difficult to debug and are a major source of frustration.

Common sources of flakiness are:

- Improperly handled concurrency.
- Dependency on test order within the test suite.
- Side effects in tests.
- Use of non-deterministic code.
- Non-identical test environments.

### 54. What is TDD?

Test-Driven Development (TDD) is a software design practice in which a developer writes tests before code. By inverting the usual order in which software is written, a developer can think of a problem in terms of inputs and outputs and write more testable (and thus more modular) code.

The TDD cycle consists of three steps:

- Red: write a test that fails.
- Green: write the minimal code that passes the test.
- Refactor: improve the code, and make it more abstract, readable, and optimized.

## TDD CycleTDD Cycle
### 55. What is the main difference between BDD and TDD?

If TDD is about designing a thing right, Behavior-Driven Development (BDD) is about designing the right thing. Like TDD, BDD starts with a test, but the key difference is that tests in BDD are scenarios describing how a system responds to user interaction.

While writing a BDD test, developers and testers are not interested in the technical details (how a feature works), rather in behavior (what the feature does). BDD tests are used to test and discover the features that bring the most value to users.
### 56. What is test coverage?

Test coverage is a metric that measures how much of the codebase is covered by tests. A 100% coverage means that every line of the code is tested at least by one test case.
### 57. Does test coverage need to be 100%?

No. There’s a myth that 100% coverage means that the code is bug-free. This is false; no amount of testing can guarantee that. Attempting to reach full test coverage is considered bad practice because it leads to a false sense of security and extra work when code needs to be refactored.
### 58. How can you optimize tests in CI?

First, we need to identify which tests are the slowest and prioritize accordingly. Once we have a plan, there are several methods for making tests faster. Some of them are:

- Breaking large tests into smaller units.
- Removing obsolete tests.
- Refactoring tests to have fewer dependencies.
- Parallelizing tests.

### 59. What’s the difference between end-to-end testing and acceptance testing?

End-to-end usually involves testing the application by using the UI to simulate user interaction. Since this requires the application to run in a complete production-like environment, end-to-end testing provides the most confidence to developers that the system is working correctly.

Acceptance testing is the practice of verifying acceptance criteria. Acceptance criteria is a document with the rules and behaviors that the application must follow to fulfill the users’ needs. An application that fulfills all acceptance criteria meets the users’ business needs by definition.

The confusion stems from the fact that acceptance testing implements the acceptance criteria verification with end-to-end testing. That is, an acceptance test consists of a series of end-to-end testing scenarios that replicate the conditions and behaviors expressed in the acceptance criteria.

# Some .gitlab-ci.yml examples

## 1. Docker_composed.yml file setup.

```Javascript
version: "3"

services:
  client:
    container_name: vkproduction-dev-web
    build:
      context: ./
      dockerfile: Dockerfile
    environment:
      HOST: 0.0.0.0
    ports:
      - 3000:3000
    volumes:
      - ./:/src/vkproduction/app/web
    working_dir: /src/client/app
    env_file:
      - ./.env
```
### Docker file associated with docker_composed.yml file. 

```Docker
FROM node:16.13.1-alpine

ARG STAG
ENV STAG ${STAG}

ARG REGION
ENV REGION ${REGION}

RUN echo ${STAG}
RUN echo ${REGION}

ENV PYTHONUNBUFFERED=1

RUN apk add --no-cache curl jq python3 py-pip make

RUN pip install awscli
RUN aws configure set aws_access_key_id _______________________.
RUN aws configure set aws_secret_access_key ___________________________.
RUN aws configure set region us-west-2

WORKDIR /src/client/app

RUN apk add --no-cache git

COPY package.json ./ 

RUN npm install --legacy-peer-deps

COPY . .

RUN aws s3 cp s3://treadmap-env/${REGION}/${STAG}/web/.env .

RUN npm run build

CMD ["npm", "run", "deploy"]
```

## 2. .gitlab-ci.yml file code Deploying python app into Heroku server.
```yml
stages:
  - test
  - build
  - deploy staging
  - automated testing
  - deploy production

variables:
  IMAGE_TAG: $CI_REGISTRY_IMAGE/employee-image:$CI_COMMIT_REF_SLUG
  STAGING_APP: emp-portal-staging
  PRODUCTION_APP: emp-portal-production
  HEROKU_STAGING: "registry.heroku.com/$STAGING_APP/web"
  HEROKU_PRODUCTION: "registry.heroku.com/$PRODUCTION_APP/web"

lint_test:
  image: python:3.8.0-slim
  stage: test
  before_script:
    - pip install flake8-html
  script:
    - flake8 --format=html --htmldir=flake_reports/
  artifacts:
    when: always
    paths:
      - flake_reports/

pytest:
  image: python:3.8.0-slim
  stage: test
  before_script:
    - pip install pytest-html
    - pip install -r requirements.txt
  script:
    - pytest --html=pytest_reports/pytest-report.html --self-contained-html
  artifacts:
    when: always
    paths:
      - pytest_reports/

build:
  image: docker:latest
  services:
    - docker:dind
  stage: build
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker build -t $IMAGE_TAG .
    - docker images
    - docker push $IMAGE_TAG

deploy_stage:
  image: docker:latest
  services:
    - docker:dind
  stage: deploy staging
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker pull $IMAGE_TAG
    - docker tag  $IMAGE_TAG $HEROKU_STAGING
    - docker login -u _ -p $HEROKU_STAGING_API_KEY registry.heroku.com
    - docker push $HEROKU_STAGING
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_STAGING_API_KEY wingrunr21/alpine-heroku-cli container:release web --app $STAGING_APP
    - echo "App deployed to stagig server at https://$STAGING_APP.herokuapp.com/"

test_stage:
  image: alpine
  stage: automated testing
  before_script:
    - apk --no-cache add curl
  script:
    - curl https://$STAGING_APP.herokuapp.com/ | grep "Employee Data"
  only:
    - main

deploy_production:
  image: docker:latest
  services:
    - docker:dind
  stage: deploy production
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker pull $IMAGE_TAG
    - docker tag  $IMAGE_TAG $HEROKU_PRODUCTION
    - docker login -u _ -p $HEROKU_PRODUCTION_API_KEY registry.heroku.com
    - docker push $HEROKU_PRODUCTION
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_PRODUCTION_API_KEY wingrunr21/alpine-heroku-cli container:release web --app $PRODUCTION_APP
    - echo "App deployed to production server at https://$PRODUCTION_APP.herokuapp.com/"Project - deploy to production
```
## 3. Using Static Enviroment in .gitlab-ci.yml file.
```yml
stages:
  - test
  - build
  - deploy staging
  - automated testing
  - deploy production

variables:
  IMAGE_TAG: $CI_REGISTRY_IMAGE/employee-image:$CI_COMMIT_SHORT_SHA
  STAGING_APP: emp-portal-staging
  PRODUCTION_APP: emp-portal-production

  HEROKU_STAGING: "registry.heroku.com/$STAGING_APP/web"
  HEROKU_PRODUCTION: "registry.heroku.com/$PRODUCTION_APP/web"


lint_test:
  image: python:3.8.0-slim
  stage: test
  before_script:
    - pip install flake8-html
  script:
    - flake8 --format=html --htmldir=flake_reports/
  artifacts:
    when: always
    paths:
      - flake_reports/

pytest:
  image: python:3.8.0-slim
  stage: test
  before_script:
    - pip install pytest-html
    - pip install -r requirements.txt
  script:
    - pytest --html=pytest_reports/pytest-report.html --self-contained-html
  artifacts:
    when: always
    paths:
      - pytest_reports/

build:
  image: docker:latest
  services:
    - docker:dind
  stage: build
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker build -t $IMAGE_TAG .
    - docker images
    - docker push $IMAGE_TAG

deploy_stage:
  image: docker:latest
  services:
    - docker:dind
  stage: deploy staging
  environment:
    name: staging
    url: https://$STAGING_APP.herokuapp.com/
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker pull $IMAGE_TAG
    - docker tag  $IMAGE_TAG $HEROKU_STAGING
    - docker login -u _ -p $HEROKU_STAGING_API_KEY registry.heroku.com
    - docker push $HEROKU_STAGING
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_STAGING_API_KEY wingrunr21/alpine-heroku-cli container:release web --app $STAGING_APP
    - echo "App deployed to stagig server at https://$STAGING_APP.herokuapp.com/"
  only:
    - main

test_stage:
  image: alpine
  stage: automated testing
  before_script:
    - apk --no-cache add curl
  script:
    - curl https://$STAGING_APP.herokuapp.com/ | grep "Employee Data"
  only:
    - main

deploy_production:
  image: docker:latest
  services:
    - docker:dind
  stage: deploy production
  environment:
    name: production
    url: https://$PRODUCTION_APP.herokuapp.com/
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker pull $IMAGE_TAG
    - docker tag  $IMAGE_TAG $HEROKU_PRODUCTION
    - docker login -u _ -p $HEROKU_PRODUCTION_API_KEY registry.heroku.com
    - docker push $HEROKU_PRODUCTION
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_PRODUCTION_API_KEY wingrunr21/alpine-heroku-cli container:release web --app $PRODUCTION_APP
    - echo "App deployed to production server at https://$PRODUCTION_APP.herokuapp.com/"Project - deploy to production
  only:
    - main
```
## 4. Using tamplating in .gitlab-ci.yml File.
```yml
stages:
  - test
  - build
  - deploy feature
  - automated feature testing
  - deploy staging
  - automated testing
  - deploy production

variables:
  IMAGE_TAG: $CI_REGISTRY_IMAGE/employee-image:$CI_COMMIT_SHORT_SHA
  STAGING_APP: emp-portal-staging
  PRODUCTION_APP: emp-portal-production

  HEROKU_STAGING: "registry.heroku.com/$STAGING_APP/web"
  HEROKU_PRODUCTION: "registry.heroku.com/$PRODUCTION_APP/web"


lint_test:
  image: python:3.8.0-slim
  stage: test
  before_script:
    - pip install flake8-html
  script:
    - flake8 --format=html --htmldir=flake_reports/
  artifacts:
    when: always
    paths:
      - flake_reports/

pytest:
  image: python:3.8.0-slim
  stage: test
  before_script:
    - pip install pytest-html
    - pip install -r requirements.txt
  script:
    - pytest --html=pytest_reports/pytest-report.html --self-contained-html
  artifacts:
    when: always
    paths:
      - pytest_reports/

build:
  image: docker:latest
  services:
    - docker:dind
  stage: build
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker build -t $IMAGE_TAG .
    - docker images
    - docker push $IMAGE_TAG

deploy_feature:
  image: docker:latest
  services:
    - docker:dind
  stage: deploy feature
  environment:
    name: review/$CI_COMMIT_REF_NAME
    url: https://$CI_ENVIRONMENT_SLUG.herokuapp.com/
    on_stop: stop_feature
  before_script: 
    - export FEATURE_APP="$CI_ENVIRONMENT_SLUG"
    - export HEROKU_FEATURE="registry.heroku.com/$FEATURE_APP/web"
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - echo "FEATURE_APP=$CI_ENVIRONMENT_SLUG" >> deploy_feature.env
    - docker pull $IMAGE_TAG
    - docker tag  $IMAGE_TAG $HEROKU_FEATURE
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_STAGING_API_KEY wingrunr21/alpine-heroku-cli create $FEATURE_APP
    - docker login -u _ -p $HEROKU_STAGING_API_KEY registry.heroku.com
    - docker push $HEROKU_FEATURE
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_STAGING_API_KEY wingrunr21/alpine-heroku-cli container:release web --app $FEATURE_APP
    - echo "App deployed to FEATURE server at https://$FEATURE_APP.herokuapp.com/"
  artifacts:
    reports:
      dotenv: deploy_feature.env
  only:
    - /^feature-.*$/

stop_feature:
  image: docker:latest
  services:
    - docker:dind
  stage: deploy feature
  variables:
    GIT_STRATEGY: none
  environment:
    name: review/$CI_COMMIT_REF_NAME
    action: stop
  before_script: 
    - export FEATURE_APP="$CI_ENVIRONMENT_SLUG"
  script:
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_STAGING_API_KEY wingrunr21/alpine-heroku-cli apps:destroy --app $FEATURE_APP --confirm $FEATURE_APP
    - echo "FEATURE application at server https://$FEATURE_APP.herokuapp.com/ is destroyed"
  when: manual

test_feature:
  image: alpine
  stage: automated feature testing
  before_script:
    - apk --no-cache add curl
  script:
    - curl https://$FEATURE_APP.herokuapp.com/ | grep "Employee Data"
  dependencies:
    - deploy_feature
  only:
    - /^feature-.*$/

.job_template: &template
  image: docker:latest
  services:
    - docker:dind
  environment:
    url: https://$APP.herokuapp.com/
  before_script: 
    - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
  script:
    - docker pull $IMAGE_TAG
    - docker tag  $IMAGE_TAG $HEROKU
    - docker login -u _ -p $HEROKU_API_KEY registry.heroku.com
    - docker push $HEROKU
    - docker run --rm -e HEROKU_API_KEY=$HEROKU_API_KEY wingrunr21/alpine-heroku-cli container:release web --app $APP
    - echo "App deployed to server at https://$APP.herokuapp.com/"
  only:
    - main

deploy_stage:
  <<: *template
  stage: deploy staging
  variables:
    APP: $STAGING_APP
    HEROKU_API_KEY: $HEROKU_STAGING_API_KEY
    HEROKU: $HEROKU_STAGING
  environment:
    name: staging

test_stage:
  image: alpine
  stage: automated testing
  before_script:
    - apk --no-cache add curl
  script:
    - curl https://$STAGING_APP.herokuapp.com/ | grep "Employee Data"
  only:
    - main

deploy_production:
  <<: *template
  stage: deploy production
  variables:
    APP: $PRODUCTION_APP
    HEROKU_API_KEY: $HEROKU_PRODUCTION_API_KEY
    HEROKU: $HEROKU_PRODUCTION
  environment:
    name: production
```
## 5.Using Time out in .gitlab-ci.yml file.
```yml
sleepy_job1:
    script:
        - echo "Job starts"
        - sleep 30m
        - echo "Job ends"
    timeout: 20m
        
sleepy_job2:
    script:
        - echo "Job starts"
        - sleep 15m
        - echo "Job ends"
```



