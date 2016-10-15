<!doctype html>
<meta charset="utf-8">
<title>miniWebRTC</title>

<h3>Create or join a room?</h3>
<button id="createBtn">BOB: Create</button>
<button id="joinBtn">ALICE: Join</button>
<hr>
<h3 id="myModalLabel">BOB: Send your local offer to ALICE</h3>
<input id="localOffer" rows=10 cols=50>
<br>
<h3>Then, paste the "answer" you received</h3>
<input id="remoteAnswer" rows=10 cols=50>
<br>
<br>
<button id="answerRecdBtn">Okay, I pasted it.</button>
<hr>
<h3>ALICE: Paste the "offer" you received</h3>
<input id="remoteOffer" rows=10 cols=50>
<br>
<br>
<button id="offerRecdBtn">Okay, I pasted it.</button>
<h3>Then, send your local answer to BOB</h3>
<input id="localAnswer" rows=10 cols=50>
<hr>
Chat:
<br>
<div id="chatlog" style="height:200px; overflow:auto; border:1px solid"></div>
<br>
<input type="text" id="messageTextBox" placeholder="Type your message here">
<button id="sendMessageBtn" onclick="sendMessage()">Send message</button>
<script>
localOffer.value = remoteAnswer.value = remoteOffer.value = localAnswer.value = "";

// BOB: create
createBtn.onclick = function() {
  dc1 = pc1.createDataChannel('test', {reliable: true})
  activedc = dc1
  dc1.onopen = function(e) { }
  dc1.onmessage = function(e) {
    if (e.data.size) {
      fileReceiver1.receive(e.data, {})
    } else {
      if (e.data.charCodeAt(0) == 2) {
        return
      }
      var data = JSON.parse(e.data)
      if (data.type === 'file') {
        fileReceiver1.receive(e.data, {})
      } else {
        chatlog.innerHTML += '[' + new Date() + '] ' + data.message + '</p>';
        chatlog.scrollTop = chatlog.scrollHeight
      }
    }
  }
  pc1.createOffer(function(desc) {
    pc1.setLocalDescription(desc, function() {}, function() {})
  }, function() { }, sdpConstraints)
};

// BOB: pasted Alice's answer
answerRecdBtn.onclick = function () {
  var answer = remoteAnswer.value;
  var answerDesc = new RTCSessionDescription(JSON.parse(answer))
  pc1.setRemoteDescription(answerDesc);
};

// ALICE: pasted Bob's answer
offerRecdBtn.onclick = function() {
  var offer = remoteOffer.value;
  var offerDesc = new RTCSessionDescription(JSON.parse(offer))
  pc2.setRemoteDescription(offerDesc)
  pc2.createAnswer(function(answerDesc) {
    pc2.setLocalDescription(answerDesc)
  },
  function () { },
  sdpConstraints)
};

if (navigator.webkitGetUserMedia) {
  RTCPeerConnection = webkitRTCPeerConnection
}

var cfg = {'iceServers': [{'url': "stun:stun.gmx.net"}]},
con = { 'optional': [{'DtlsSrtpKeyAgreement': true}] }

var pc1 = new RTCPeerConnection(cfg, con), dc1 = null, tn1 = null, activedc, pc1icedone = false;

var sdpConstraints = {
  optional: [],
}

function sendMessage () {
  if (messageTextBox.value) {
    activedc.send(JSON.stringify({message: messageTextBox.value}));
    chatlog.innerHTML += '[' + new Date() + '] ' + messageTextBox.value + '</p>';
    messageTextBox.value = "";
  }
  return false
}

pc1.onicecandidate = function (e) {
  if (e.candidate == null) {
    localOffer.value = JSON.stringify(pc1.localDescription);
  }
}

var pc2 = new RTCPeerConnection(cfg, con), dc2 = null, pc2icedone = false;

pc2.ondatachannel = function (e) {
  var datachannel = e.channel || e;
  dc2 = datachannel
  activedc = dc2
  dc2.onopen = function (e) { }
  dc2.onmessage = function (e) {
    if (e.data.size) {
      fileReceiver2.receive(e.data, {})
    } else {
      var data = JSON.parse(e.data)
      if (data.type === 'file') {
        fileReceiver2.receive(e.data, {})
      } else {
        chatlog.innerHTML += '[' + new Date() + '] ' + data.message + '</p>';
        chatlog.scrollTop = chatlog.scrollHeight;
      }
    }
  }
}

pc2.onicecandidate = function (e) {
  if (e.candidate == null) {
    localAnswer.value = JSON.stringify(pc2.localDescription);
  }
}
</script>