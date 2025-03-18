Max number of ports = 255

A router reads packages from input ports and writes them to output ports based on their address. Input and output ports are numbered 0...255. 

During each cycle, an arbitrary number of packages arrives at the input queues. 

The router then tries to read one package from each input port queue, in order (starting with port 0), and if available writes it to the matching output port queue. For clarity, one cycle consists of (a) reading any number of packets into input queues, and (b) sending one packet per input queue to the specified output queue. Processing proceeds cycle by cycle, until no more inputs arrive and all input queues are empty (so that all packets have been sent to output queues).

## Process
input comes in.

**LOAD**
Data is sorted into input ports. Queued in order of arrival by port.

**PROCESS**
Only one value from each input port queue is moved to its allocated output port.

**LOAD**
more data is input. This is sorted as loaded above.

**PROCESS**
As above.

Cycle continues until input queues are empty.

