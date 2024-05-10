# Description actions

Il s'agit de deux extracts de pages de L'Equipe.

La page d'accueil qui contenait déjà des classifications par sports.

On peut cliquer sur `Rugby`pour ouvrir la page Rugby (la seule qui fonctionne en l'état).

Un début de code de chatbot a été créé, mais pas eu le temps de finbaliser la partie back, ou chat en lui même.

Code en question remis ici : 

```texte
<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
 

 
.chatBot {
  border: 3px solid rgb(214, 30, 0);
  border-radius: 10px;
  margin: 50px auto;
  overflow: hidden;
  width: 400px;
  overflow-y: clip;
  height: 700px;
  z-index: 1000; /* integer */
  background: rgb(255, 255, 255) url(gfg-gg-logo.svg);
  background-size: contain;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  background-repeat: no-repeat;
  background-position: center;
  position: fixed;
  bottom: 0;
	right: 0;
  

* {
position: relative;
}
  
  header {
  background-color: rgb(214, 30, 0);
  text-align: center;
  padding: 10px 0;
  border-radius: 7px 7px 0 0;
}
 
header h2 {
  color: #fff;
  margin: 0;
}
 
.chatbox {
  padding: 15px;
  list-style: none;
  overflow-y: auto;
  height: 400px;
}
 
.chatbox li {
  margin-bottom: 10px;
}
 
.chat p {
  padding: 10px;
  border-radius: 10px;
  max-width: 70%;
  word-wrap: break-word;
}
 
.chat-outgoing p {
  background-color: rgb(214, 30, 0);
  align-self: flex-end;
  color: #fff;
}
 
.chat-incoming p {
  background-color: #eaeaea;
}
 
.chat-input {
  padding: 10px;
  border-top: 1px solid rgb(214, 30, 0);
}
 
.chat-input textarea {
  width: 522px;
  padding: 10px;
  border: 1px solid rgb(214, 30, 0);
  border-radius: 7px;
  resize: none;
  outline: none;
  overflow-y: scroll;
  background-color: #dcdcdc85;
  font-size: 16px;
  color: black;
  font-weight: 600;
  margin-top: -10px;
  margin-left: -15px;
  height: 71px;
}
 
#cross {
  float: right;
  position: relative;
  top: -38px;
  left: -15px;
  cursor: pointer;
  color: white;
  font-weight: bolder;
  font-size: 28px;
}
 
#cross:hover {
  color: red;
  transition: all .5s;
}
 
.chatbox .chat p.error {
  color: #ffffff;
  background-color: #ff3737e8;
}
 
#sendBTN {
  width: 100%;
  padding: 8px;
  border: 0;
  outline: none;
  font-size: 20px;
  font-weight: 600;
  border-radius: 7px;
  background-color: rgb(214, 30, 0);
  cursor: pointer;
  color: white;
  margin-top: 12px;
}
 
.lastMessage {
  margin-top: 50px;
  font-size: 35px;
  font-weight: 600;
  color: darkgreen;
  margin-left: 550px;
}
  
}
 

	</style>
	
	<script>
	$( document ).ready(function(){
	
	$( ".chatBot .chatbox" ).ready(function(){
			
		var cur_history = [];
		var msg = {
			"text" : "Hey! How can I assist you today?",
			"author" : "chatbot",
			"date" : ""
		};
		cur_history.push(msg);
		var msg = {
			"text" : "Test !",
			"author" : "chatbot",
			"date" : ""
		};
		cur_history.push(msg);
		
		function refresh_history(cur_history){
		
			$( ".chatBot .chatbox" ).empty();
			
			for (var i = 0; i< cur_history.length; i++){
				var cur_msg = cur_history[i];
				$( ".chatBot .chatbox" ).append('<li class="chat-incoming chat"><p>'+cur_msg["text"]+'</p></li>');
			}
			
			
		}
		
		refresh_history(cur_history);
		
		});
	
	});
	
	</script>

	<div class="chatBot">
        <header>
            <h2>ChatBot</h2>
            <span alt="Close"
                  id="cross"
                  onclick="cancel()">X</span>
        </header>
        <ul class="chatbox">
            <li class="chat-incoming chat">
                <p>Hey! How can I assist you today?</p>
            </li>
        </ul>
        <div class="chat-input">
            <textarea rows="0" cols="17"
                      placeholder="Enter a message..."></textarea>
            <button id="sendBTN">Send</button>
        </div>
    </div>
```
