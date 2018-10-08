# p4debug
P4 simple forwarder with monitoring/debugging features

This application does nothing but forwards packets from port 0 to port 1 and vice versa.
During forwarding, according to the settings defined by `ifdef` conditions in the source code, the packets are processed through several debugging tables.
The idea was adopted from [https://github.com/jafingerhut/p4-guide/tree/master/checksum](https://github.com/jafingerhut/p4-guide/tree/master/checksum)

The debugging tables can be used to print out to stdout or to output file what header fields the P4 switch encounters.
Without such debug tables, simple troubleshooting is a bit cumbersome as P4 does not have `print` statements.

## Usage

### Compile if necessary:
```
p4c-bm2-ss monitoring.p4 -o monitoring.json
```

### Run 
```
simple_switch -i 0@eno3 -i 1@eno4 monitoring.json --log-console
```
Here `eno3` and `eno4` are the interfaces I have on my machine. If you don't want to put log to the console, replace `--log-console` with `--log-file my_log.log`




