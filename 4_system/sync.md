Sync
- daily transfer of status / if data
- weekly transfer of status + report
- monthly transfer of report

Data
- daily diff of updates encrypted to district public key.
- 

Status is:
- day's successful transfers / attempts to connect
- day's authentications / attempts to authenticate
- day's wifi connections.
- day's patients viewed / created / patients edited / visits created / reports viewed / reports edited
- day's uptime
- day's uucp stats.
- couchdb running.
- mgetty running
- chatscript result of modem is OK.

Report is:
- rrd for CPU/temp/solar charge controller 
- disk space
- all processes
- uurate -a
- 


Error mitigation 
- Alert mode: if missed transfer / more than 3 failed auth / 
- Error mode; if there is data and didn't connect to district in 3 days then go in error mode. 
- critical mode: error mode for more than 5 days / 

In alert mode

In error mode:
- tries to send to district or any other node. 
- sets error level debug logs.
- displays message on EMR

In critical mode: (in error node for 5 days or critical error detected).
- tries to self repair. Check free disk space, delete old logs,

