# nullinux

Nullinux is an internal penetration testing tool for Linux that can be used to enumerate OS information, domain information, shares, directories, and users through SMB. If no username and password are provided in the command line arguments, an anonymous login, or null session, is attempted. Nullinux acts as a wrapper around the Samba tools smbclient & rpclient to enumerate hosts using a variety of techniques.

Key Features:
* Single or multi-host enumeration
* Enumerate shares and list files in root directory
* Enumerate users & groups
* Multi-threaded RID Cycling
* Creates a formatted nullinux_users.txt output file free of duplicates for further exploitation
* Python 2.7 & 3 compatible

For more information, and example output, visit the [wiki page](https://github.com/m8r0wn/nullinux/wiki).

### Getting Started
In the Linux terminal run:
```
git clone https://github.com/m8r0wn/nullinux
cd nullinux
sudo bash setup.sh
```

### Usage

    usage:
        nullinux -users -quick DC1.demo.local
        nullinux -all 192.168.0.0-5
        nullinux -shares -U 'Domain\User' -P 'Password1' 10.0.0.1,10.0.0.5

    positional arguments:
      targets                   Target server

    optional arguments:
      -h, --help                show this help message and exit
      -u USERNAME, -U USERNAME  Username
      -p PASSWORD, -P PASSWORD  Password
      -v                        Verbose output
      -shares                   Enumerate shares
      -users                    Enumerate users
      -a, -all                  Enumerate shares & users
      -q, -quick                Fast user enumeration (use with -users or -all)
      -r RID_RANGE              Set Custom RID cycling range (Default: 500-530)
      -t MAX_THREADS            Max threads for RID cycling (Default: 5)
