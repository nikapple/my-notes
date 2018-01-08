# Issues

- **wrt to plantuml velocity template logic**
  - multiple before or after messages between same particpants causes object to activate(or deactivate) multiple times
    - solution : create Participant with state isActivated
  - how to activate first object i.e. initiator?

# Trace logs to Sequence diagrams

- logs format

`[16-Apr-2011 03:05:02.111][MessageHandler][MessageHandler.cpp:563]received RandomAccessMessage(signalQuality=15) from DSP_01`

*Get logs from DynamoDb for an NDC in following format*  

log entry construct | sequence diagram mapping  
--- | ---  
type [before-or-after] | activate/deactivate participant
[timestamp] | order of messages
[current-object] (derived from log order based on timestamp) | arrow source
[message] | message
[target-object]  (derived from logAspect message) | arrow destination
[current-objects] as set| participants

log pattern to parse is `%x *$^ %p *$^ %l *$^ %m%n`  delimter = `"*$^"`  

pattern | details  
--- | ---  
%x | NDC
%p | priority
%l | logger-name, class and line number
%m | LogAspect message - type, target class, method and timestamp



- activate and deactivate object logic?
  - if before statement activate called object and then send message
  - if after statement send message and then deactivate current object


- objects to be passed to template?
  - Set of Participants
  - List of LogEntries


-------
# rough  
-##deactivate $logEntries[length-1].calledObj  
-##activate $logEntries[1].currentObj

#### method flow:
- invoke itself
- invoke another method in same object
- invoke another method in another object
- terminate

OLD PARSING CODE
Pattern.compile("timestamp=");
			this.id = UUID.randomUUID().toString();
			Matcher matcher = Pattern.compile("NDC=").matcher(logEvent);
			while (matcher.find()) {
				this.ndc = logEvent.substring(matcher.end(), logEvent.indexOf(" ", matcher.end()));
			}
			matcher = Pattern.compile("timestamp=").matcher(logEvent);
			while (matcher.find()) {
				this.timestamp = logEvent.substring(matcher.end(), matcher.end() + 19);
			}
			this.logMessage = logEvent;

---------

# Explore

- plant uml api
