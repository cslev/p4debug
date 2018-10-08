# p4debug
P4 simple forwarder with monitoring/debugging features

This application does nothing but forwards packets from port 0 to port 1 and vice versa.
During forwarding, according to the settings defined by `ifdef` conditions in the source code, the packets are processed through several debugging tables.
The debugging tables can be used to print out to stdout or to output file what header fields the P4 switch encounters.
Without such debug tables, simple troubleshooting is a bit cumbersome as P4 does not have `print` statements.

