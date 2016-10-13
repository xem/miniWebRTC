miniWebRTC
===

A tiny serverless* WebRTC boilerplate,
<br>
inspired by https://github.com/cjb/serverless-webrtc and https://github.com/webrtc/samples

*no signaling server, but the STUN server is still necessary and used.

---

Principle
====

- bob asks his ip to a stun server and sends it to alice via an url
- alice clicks and asks her ip to the stun server and sends it to bob via an url
- bob clicks
- both can communicate with webrtc

