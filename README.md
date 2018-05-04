```text

 _   _ _____ _____ _____               
| | | |  _  /  ___|_   _|              
| |_| | | | \ `--.  | |                
|  _  | | | |`--. \ | |                
| | | \ \_/ /\__/ / | |                
\_| |_/\___/\____/  \_/                
                                       
______                _                
| ___ \              | |               
| |_/ /___  ___  ___ | |_   _____ _ __ 
|    // _ \/ __|/ _ \| \ \ / / _ \ '__|
| |\ \  __/\__ \ (_) | |\ V /  __/ |   
\_| \_\___||___/\___/|_| \_/ \___|_|   
                                       
                                       
```



Resolves an IPv4 or file of IPv4 addresses, using the PTR records from an 
entire list of internal DCs. Can Query A records to resolve hosts, 
or a file of hostnames to IPs.

### Requirements

- Python (2.X or 3.X compatible)
- dnspython package

Install pkg with: `sudo pip install dnspython` or `sudo pip3 install dnspython` (osx/linux hosts)
(Note: "dnspython" pkg requires >= pip 9.0.3)
(Python 3.X should use pip3, 2.X shpould use pip)
Upgrade pip with: `sudo pip install --upgrade pip` or `sudo pip3 install --upgrade pip3`
If you need to install python-pip/pip3:
    - `sudo easy_install pip` or `sudo easy_install pip3` [OSX]
    - `sudo apt install pip` or `sudo apt install pip3` [debian-based Linux]

### Installation

`git clone [repo]`
`cd [repo] `
`chmod 755 resolve`

Add your list of internal DCs

### Usage

`./resolve [ip]` | `./resolve -i [ip]` | `./resolve -if [ip_file]` 
`./resolve -hf [host_file]` | `./resolve -host [hostname]` 

The input file should contain either newline-separated IP addresses,
or newline-separated hostnames.

You can also use public DNS for resolving outside IPs: 
`./resolve -p [ip]`

if you want to export these results to a file, try something like:
`./resolve -hf [host_file] | tee [outfile.txt]`
`./resolve -if [ip_file] >> [outfile.txt]` 

For quick access to this tool; rename "resolve" to "res" or use an alias of your choice;
and save it in one of your $PATH directories
