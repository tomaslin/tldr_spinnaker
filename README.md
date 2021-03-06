#tldr Spinnaker

Collection of recipes and odds and ends around Spinnaker.

## Events

[Add Github Trigger](events/github.md)

[Add Stash Trigger](events/stash.md)

[Post Spinnaker events to a Webhook](events/webhook.md)

## Expressions

Fetch Results From an URL

Parse JSON from URL

Send JSON to Jenkins

Make Parameter Optional

Getting baked image details

Getting deployed server group details

Getting details from trigger

Getting details from parent pipeline

Accessing parameter values

Filtering Baked AMIs

## Jenkins Integration

Passing values from jenkins to Spinnaker via property files

## Pipeline Usage

Setting up parameter values

Only execute pipeline stage at a certain time

Optionally Execute a Pipeline

Setting up Deployment Strategy

Passing exterior image to Deploy Stage 

Batch Update Pipelines

## Pipeline Recipes

[Run a cleanup pipeline when parent pipeline fails](recipes/cleanup.md)

Jenkins and Script stages to extend functionality

Use Spinnaker to reduce number of Jenkins jobs

Feature Clusters

Trigger a pipeline on failure

Use a holder cluster

Bake and Quickpatch for smoke testing

Deployment Strategy shared across applications

Ad-hoc Pipelines with Spinnaker API

Generating and storing pipeline permutations

## Docker Compose

Provide own settings.js

## More links

* [Google Code Lab](http://spinnaker.io/documentation/source-to-prod-codelab.html)
* [Spinanker Deployment Pipelines ( Samuel Toriel )](http://riltsken.github.io/devops/infrastructure/deploymenttools/2016/02/08/spinnaker-deployment-pipelines.html)
* [Set up okta auth ( Samuel Toriel )](http://riltsken.github.io/devops/infrastructure/deploymenttools/2015/12/08/setup-okta-saml-with-spinnaker.html)
* [Deploying nodejs with Spinnaker](http://blog.greta.io/deploying-nodejs-with-spinnaker/)
* [Video: Rick Buskens Microservices Exchange Berlin](https://www.youtube.com/watch?v=UOkZJazycQs)
* [Video: Netflix OSS Meetup](https://www.youtube.com/watch?v=5s-SS_aXoi0&feature=youtu.be&t=863)
* [Spinnaker: Land of 1000 builds. Slides](https://speakerdeck.com/gregturn/spinnaker-land-of-a-1000-builds)
