# Bandwidth utilization

## Multiplexing

**Multiplexing** is a set of techniques that allows the simultaneous
transmission of multiple signals across a single data link. In a multiplexing
system, $n$ channels share the bandwidth of one link. The lord **channel**
refers to the portion of a link that carries a transmission between a given
sender-receiver pair. One link can have many channels.

### FDM

In *frequency division multiplexing (FDM)*, signals generated by each sending
device modulate different carriers. This modulated signals are then combined
into a single composite signal that can be sent by the link. Channels can be
separated by strips of unused bandwidth-guard bands to prevent signal from
overlapping.

Each source generates a signal of a similar frequency range. These similar
signals modulate different carriers (with different frequencies $f_1$, $f_2$,
and $f_3$), The resulting modulated signals are then combined into a single
composite signal that is sent over a link.

#### Demultiplexing FDM

The demultiplexer uses a series of filters to decompose the multiplexed signals
into its constituent component signals. The individual signals are then passed
to a demodulator that separates the input signals from their carriers and passes
them to the output lines.

Telephone companies have traditionally multiplexed signals from lower-bandwidth
lines onto higher-bandwidth lines.

| Analog multiplexing hierarchy | Classification |
| --- | --- |
| 12 voice channels | Group |
| 5 groups | Supergroup |
| 10 supergroups | Master group |
| 6 master groups | Jumbo group |

### TDM

**Time division multiplexing (TDM)** is a digital process that allows several
connections to share the high bandwidth of a link. INstead of sharing a portion
of the bandwidth as in FDM, **time is shared**. Each connection occupies a
portion of time in the link.

#### Synchronous TDM

In **synchronous TDM**, data units from each input connection are combined into
a frame. If we have in connections, a frame is divided into $n$ time slots and
one slot is allocated into each unit, one for each input line.

The data rate of the output link must be in $n$ times higher than the data rate
of a single input link to guarantee the flow of data.

TDM can be visualized as two fast-rotating switches, one on the multiplexing
side and the other on the de-multiplexing side. And the switch is
**unsynchronized** and rotate at the same speed but in positive direction.

| Side | Description |
| --- | --- |
| Multiplexing | As the switch open in front of a connection, this connection can send a unit of data onto the link. This process is called interleaving. |
| De-multiplexing | As the switch open, the connection can receive a unit of data from the link. |

If a source does not have data to send, the corresponding slot in the output
frame is empty.

### Multilevel multiplexing

**Multilevel multiplexing** is a technique used when the data rate of an input
line is a multiple of others.

### Multiple-slot allocation

We can allocate more than 1 slot in a frame to a single input line.

### Pulse stuffing

If bit rate of sources are not multiple integers of each other, we can make the
highest input data rate the dominant data rate and then add dummy bits to the
input lines with lower rates. This technique is called pulse stuffing, bit
padding, or **bit stuffing**.

If the multiplexer and the de-multiplexer are not synchronized, a bit belonging
to one channel may be received by the wrong channel. For this reason, one or
more synchronization bits are usually added to each frame.

## Spreading