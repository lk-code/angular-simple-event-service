# Simple Angular EventService

## Setup
1. copy the two service files to the service-directory in your angular app.
2. inject the event-Service in your component, service, etc,


```
import { EventService } from '../event/event.service';

constructor(private eventService: EventService) {
    this.subscribeEvents();
    this.triggerEvents();
}

subscribeEvents() {
    this.eventService.Subscribe("yourapp:some-event", function(data) {
        console.log(data); // => "hello world"
    });
}

triggerEvents() {
    this.eventService.Trigger("yourapp:some-event", "hello world");
}
```

## Trigger

name: string - an unique event-key

data:? any - you can send a lot of things through the Trigger-method - strings, numbers, objects, etc.

## Subscribe

name: string - the event-name to listen

handler: Function - the method, which should be executed if the event is triggered