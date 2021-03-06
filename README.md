socialapi-webrtc-demo
=====================

This needs the latest Firefox 19 (currently the Nightly channel) to work.

To start the server:
$ env PORT=5000 AUDIENCE="http://localhost:5000" node app.js

Create a new profile.  You don't want to be messing with all these
prefs in a profile that you use regularly. Then edit about:config:

name: `social.manifest.<foo>`, where `<foo>` is replaced by name of the social provider.

value: {"location":"http://localhost:5000/manifest.json","name":"WebRTC Social Demo","iconURL":"http://localhost:5000/icon.png","workerURL":"http://localhost:5000/worker.js","sidebarURL":"http://localhost:5000/sidebar.htm","origin":"http://localhost:5000","enabled":true,"last_modified":135101330568}

or use the remote server:

value: {"location":"http://webrtc-social.herokuapp.com/manifest.json","name":"WebRTC Social Demo","iconURL":"http://webrtc-social.herokuapp.com/icon.png","workerURL":"http://webrtc-social.herokuapp.com/worker.js","sidebarURL":"http://webrtc-social.herokuapp.com/sidebar.htm","origin":"http://webrtc-social.herokuapp.com","enabled":true,"last_modified":135101330568}

Additionally, in about:config, set the following prefs:

    social.enabled: true
    media.navigator.enabled: true
    media.navigator.permission.disabled: true
    media.peerconnection.enabled: true
    dom.disable_open_during_load: false
