# JAP\_REMOTE\_WS\_NODE\_OPENSHIFT #

## PRE-INSTALLATION ##
  * create OPENSHIFT account
  * install OPENSHIFT CLI

## INSTALLATION ##
  * unzip JAP\_REMOTE\_WS\_NODE\_OPENSHIFT-X.X.X.zip
  * open JAP\_REMOTE\_WS\_NODE\_OPENSHIFT-X.X.X
  * [configure JAP\_REMOTE\_WS.json](CONFIGURE_JAP_REMOTE_WS.md)
  * open CONSOLE
    * WINDOWS
      * rhc app create -a application-id -t nodejs-0.6
      * cd application-id
      * xcopy ..\JAP\_REMOTE\_WS\_NODE\_OPENSHIFT-X.X.X\**.** /s /y
      * git add -A
      * git commit -m "JAP"
      * git push
    * LINUX
      * rhc app create -a application-id -t nodejs-0.6
      * cd application-id
      * cp -r ../JAP\_REMOTE\_WS\_NODE\_OPENSHIFT-X.X.X/. .
      * chmod -R +x ./.openshift/action\_hooks ./JAP
      * git add -A
      * git commit -m "JAP"
      * git push

## IMPORTANT ##
OPENSHIFT WEBSOCKET protocol support is EXPERIMENTAL
  * WEBSOCKET protocol over HTTP
    * JAP\_REMOTE\_WS
      * configure JAP\_REMOTE\_WS.json
        * REMOTE\_PROXY\_SERVER/TYPE = HTTP
    * JAP\_LOCAL\_WS
      * configure JAP\_LOCAL\_WS.json
        * REMOTE\_PROXY\_SERVERS/TYPE = HTTP
        * REMOTE\_PROXY\_SERVERS/ADDRESS = YYY-ZZZ.rhcloud.com
        * REMOTE\_PROXY\_SERVERS/PORT = 8000
  * WEBSOCKET protocol over HTTPS
    * JAP\_REMOTE\_WS
      * configure JAP\_REMOTE\_WS.json
        * REMOTE\_PROXY\_SERVER/TYPE = HTTPS
    * JAP\_LOCAL\_WS
      * configure JAP\_LOCAL\_WS.json
        * REMOTE\_PROXY\_SERVERS/TYPE = HTTPS
        * REMOTE\_PROXY\_SERVERS/ADDRESS = YYY-ZZZ.rhcloud.com
        * REMOTE\_PROXY\_SERVERS/PORT = 8443