# droideon
centreon mobile app for android

non official application for users of Centreon

### App prerequisite

this app work for centreon :
- 2.8.X
- 2.7.X
- 2.6.X

< 2.6.X not tested

allows you to keep your supervision at your fingertips with real-time notifications via a service installed on your centreon / nagios infrastructure.

### features :

list of services acknowledge or not with search filter and sorting

detail of the service with metrics and select date when click on metric.

for each service or in list :

    - acknowledge and disacknowledge
    - add or remove a downtime
    - enable / disable notifications
    - enable / disable checks
    - immediate control [forced]
    - add comment

list of hosts acknowledge or not with search filter and sorting

detail of a host with the list of associated services

shorcut in menu host for connect via SSH with connectbot App

shorcut in menu host for connect via RDP with Windows Remote Desktop App

for each host or in list, we can do the same actions as on a service, but it is applied to all services of the host.

 list of events related to a service or host with date filter, notifications, status.
 shortcut list of the latest notifications received [all centreon users]

sending notifications:
- with possibility to set a different ringtone for problems and resolutions
- button to automatically acknowledge a problem.
- button to automatically set downtime to a problem


widget which allows to have an overview of its infrastructure with automatic or manual refresh and shortcut to the application


## Notifications instructions

the token is avaible in the app  :  Settings => Notifications Activation

![Android capture](androidcapturenotif.jpg?raw=true "notif catpure")

download sendpush  and put it in your plugins directory

create notification service 

exemple for service :

    $USER1$/sendpush -t “$NOTIFICATIONTYPE$” -h “$HOSTID$” -s “$SERVICEID$” -S “$SERVICEDESC$” -H “$HOSTNAME$” -e “$SERVICESTATE$” -d “$LONGDATETIME$” -o “$SERVICEOUTPUT$” -k “***token***”

exemple for host :

    $USER1$/sendpushservice.sh -t “$NOTIFICATIONTYPE$” -h “$HOSTID$” -H “$HOSTNAME$” -e “$HOSTSTATE$” -d “$LONGDATETIME$” -o “$HOSTOUTPUT$” -k “***token***”

replace ***token***  with you own token 
### About 
More informations about centreon system :
http://www.centreon.com
