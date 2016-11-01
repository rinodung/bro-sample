#Overview
BBro is a powerful system that on top of the functionality it provides out of the box, also offers the flexibility to customize analysis pretty much arbitrarily. 
We provide a range of documentation material ranging from introductory material to get you started, to full references of Bro’s various frameworks.
#Installation
1. Install the required dependencies
`sudo apt-get install cmake make gcc g++ flex bison libpcap-dev libssl-dev python-dev swig zlib1g-dev`
2. Install Bro From Git
`git clone --recursive git://git.bro.org/bro`
```
sudo ./configure
sudo make
sudo make install
```


OR From Package
```
sudo sh -c "echo 'deb http://download.opensuse.org/repositories/network:/bro/xUbuntu_14.04/ /' >> /etc/apt/sources.list.d/bro.list"
sudo apt-get update
sudo apt-get install bro
```
https://www.bro.org/sphinx/install/install.html

# Configure the Run-Time Environment
export PATH=/usr/local/bro/bin:$PATH

# Managing Bro with BroControl
Default: $PREFIX /usr/local/bro

1. $PREFIX/etc/node.cfg, set the right interface to monitor.
2. $PREFIX/etc/networks.cfg, comment out the default settings and add the networks that Bro will consider local to the monitored environment.
3. $PREFIX/etc/broctl.cfg, change the MailTo email address to a desired recipient and the LogRotationInterval to a desired log archival frequency.

Now start the BroControl shell like: 
`sudo broctl`

Since this is the first-time use of the shell, perform an initial installation of the BroControl configuration:
`[BroControl] > install`

Then start up a Bro instance:
`[BroControl] > start`

Stop Bro
`[BroControl] > stop`

Check Script

`[BroControl] > check`

Restart(After Install)

`[BroControl] > restart`

# Options
```
usage: bro [options] [file ...]
    <file>                         | policy file, or read stdin
    -a|--parse-only                | exit immediately after parsing scripts
    -b|--bare-mode                 | don't load scripts from the base/ directory
    -d|--debug-policy              | activate policy file debugging
    -e|--exec <bro code>           | augment loaded policies by given code
    -f|--filter <filter>           | tcpdump filter
    -g|--dump-config               | dump current config into .state dir
    -h|--help|-?                   | command line help
    -i|--iface <interface>         | read from given interface
    -p|--prefix <prefix>           | add given prefix to policy file resolution
    -r|--readfile <readfile>       | read from given tcpdump file
    -s|--rulefile <rulefile>       | read rules from given file
    -t|--tracefile <tracefile>     | activate execution tracing
    -v|--version                   | print version and exit
    -w|--writefile <writefile>     | write to given tcpdump file
    -x|--print-state <file.bst>    | print contents of state file
    -C|--no-checksums              | ignore checksums
    -F|--force-dns                 | force DNS
    -G|--load-seeds <file>         | load seeds from given file
    -H|--save-seeds <file>         | save seeds to given file
    -I|--print-id <ID name>        | print out given ID
    -N|--print-plugins             | print available plugins and exit (-NN for verbose)
    -P|--prime-dns                 | prime DNS
    -Q|--time                      | print execution time summary to stderr
    -R|--replay <events.bst>       | replay events
    -S|--debug-rules               | enable rule debugging
    -T|--re-level <level>          | set 'RE_level' for rules
    -U|--status-file <file>        | Record process status in file
    -W|--watchdog                  | activate watchdog timer
    -X|--broxygen <cfgfile>        | generate documentation based on config file
    --pseudo-realtime[=<speedup>]  | enable pseudo-realtime for performance evaluation (default 1)
    $BROPATH                       | file search path (.:/usr/local/bro/share/bro:/usr/local/bro/share/bro/policy:/usr/local/bro/share/bro/site)
    $BRO_PLUGIN_PATH               | plugin search path (/usr/local/bro/lib/bro/plugins)
    $BRO_PLUGIN_ACTIVATE           | plugins to always activate ()
    $BRO_PREFIXES                  | prefix list ()
    $BRO_DNS_FAKE                  | disable DNS lookups (off)
    $BRO_SEED_FILE                 | file to load seeds from (not set)
    $BRO_LOG_SUFFIX                | ASCII log file extension (.log)
    $BRO_PROFILER_FILE             | Output file for script execution statistics (not set)
    $BRO_DISABLE_BROXYGEN          | Disable Broxygen documentation support (not set)
    
```