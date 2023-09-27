# Developer Log

## Release note

### Function until Alpha 2.10

1. Grab newly assigned cases for specifc users(based on M1 manager), send notification to users via QIYE wechat APP.
2. Store backend data to Postgresql database.
3. User can send collab ID to register the notification for newly assignment for this case.

## Function develop plan

### plan for 2.11

1. Add user self-registration logic
2. Optimize collab tracing needed case number
3. Add long-term monitoring logic for the case didn't met SLA

## Bug record and fix

1. 2023-09-19 06:26:54, all peple get the case notification again.
1.a [analysis] checked log before, the checking before the issue time took around 2 mins(normally should be around 1 min), guess the possible reason is that the DFM didn't give a correct response, which make the reply is empty and cleared all record for last case list. when next query back to normal, all recorded cases will be send again.
Can try to add a mechanism that only continuely get 5 empty reply, then give the empty result to previous result. Otherwise keep prvious result.
1.b [fix] to be done
