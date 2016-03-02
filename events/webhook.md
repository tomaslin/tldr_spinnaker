# Add a listening webhook to spinnaker

[echo-rest](https://github.com/spinnaker/echo/tree/master/echo-rest) module in spinnaker allows you to hook up to a stream of events coming in from spinnaker.

The intent is to send off events from Spinnaker into an external system. 

Sometimes, it makes sense to have an intermediate service that will filter out the interesting events and covert spinnaker events into the format you care about. 

## Configuration in echo.yml

```
rest:
  enabled: true
  endpoints:
    - 
      wrap: false
      url: http://listener.com
    - 
      wrap: false
      url: http://listener2.com
```

This will post every event to listener and listener2

## Wrapping 

If your endpoint expects events of the form 

```
	{ "eventName" : "abc", "payload" : "[event json]"}
```

you can wrap the event via this configuration:

```
	- 
      wrap: true
      flatten: true
      url: http://listener3
      eventName: spinnaker_events
      fieldName: payload
```

The flatten setting will simply make the json in content and details ( see below ) into a json String. 

# Event types

Here is an example event:

```
{
    "details": {
      "source": "orca",
      "type": "orca:task:complete",
      "created": "1422487582294",
      "organization": null,
      "project": null,
      "application": "asgard",
      "_content_id": null
    },
    "content": {
      "standalone": true,
      "context": {
        "asgName": "asgard-staging-v048",
        "credentials": "test",
        "deploy.account.name": "test",
        "deploy.server.groups": {},
        "kato.last.task.id": {
          "id": "19351"
        },
        "kato.task.id": {
          "id": "19351"
        },
        "kato.tasks": [
          {
            "history": [
            ],
            "id": "19351",
            "resultObjects": []
          }
        ],
        "notification.type": "enableasg",
        "regions": ["us-west-1"],
        "targetop.asg.enableAsg.name": "asgard-staging-v048",
        "targetop.asg.enableAsg.regions": ["us-west-1"],
        "user": "ajordens@netflix.com",
        "zones": ["us-west-1a", "us-west-1c"]
      },
      "execution": ...
      "executionId": "62ca5574-0629-419a-b9ac-fb873aa165b2",
      "taskName": "f92239a7-b57a-408d-9d72-3a77484e050b.enableAsg.monitorAsg.9568e7e5-3c37-4699-9e93-f62118adc7c6"
    }
  }
```

Events have a details, which will always be the same.

### details.type

The type of the event will outline where the event is coming from:

* orca:[task type]:[status] - where task type is either 'pipeline', 'stage' or 'task' and status is 'starting', 'completed', 'failed'
* build - from igor
* git - from git web triggers

### details.application

The application involved in the execution, this will only exist for orca: type events.

### content.execution

For orca type events, this is the corrent execution that has the entire pipeline execution. 



