# Using Stash as a Trigger

Go to settings / hooks for your repository

Add a Post Receive webhook

Add the following URL: http://[gate url]/webhooks/git/stash where gate url is the url to your spinnaker api.

You are now ready to receive events from this repository.

See git trigger config details in [github trigger](github.md)