```
{
	msgtype(t): request(q) | response(s)
    jobstate(s): AWAIT(W)|ABUSY(B)|SJOB(J)
            Agent sets the following states:
			   (response from agent) AWAIT: Agent is idle waiting for instructions
			   (response from agent) ABUSY: Agent has picked up job and executing

		   	Server sets the following states:
			   (request from server) SJOB: Server posted new job to the Agent. Agent needs to pick it up upon next checkin

	req_type(c): oscmd(o)|file(f)|mcmd(m)
			 oscmd: Agent is tasked with executing an os command, inline or path to file with commands (not script).
			 file: Agent is tasked with saving data to disk in a file
			 mcmd: Agent is tasked to execute it's maintenance (not implemented)

	resp_type: url

	 url(u): Server is to pick up response from agent at this sendservice URL
	 url(u):  Agent is to pick up data for request types from this sendservice URL

	timestamp: date/time UTC epoch (not implemented)
}


Sample Request by server to agent to execute OS command, details at the url ...
{
 't':'q',
 's':'J',
 'c' :'o',
 'u': 'http://...........................'
}

{ 't':'q', 's':'J', 'c' :'o' 'u': 'http://...........................' }
```


