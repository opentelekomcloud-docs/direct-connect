:original_name: dc_04_0802.html

.. _dc_04_0802:

Supported Metrics
=================

Function
--------

This section describes the metrics reported by Direct Connect to Cloud Eye as well as their namespace and dimensions. You can use the management console or call the APIs provided by Cloud Eye to query the metrics of the monitored objects and alarms generated for Direct Connect.

Namespace
---------

SYS.DCAAS

Metrics
-------

.. table:: **Table 1** Direct Connect metrics

   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | Metric                                | Name                         | Description                                                                                                                     | Value Range    | Monitored Object | Monitoring Interval |
   +=======================================+==============================+=================================================================================================================================+================+==================+=====================+
   | network_incoming_bits_rate            | Network Incoming Bandwidth   | Bit rate for inbound data to the Direct Connect side of a connection                                                            | >= 0 bits/s    | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: bit/s                                                                                                                     |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_outgoing_bits_rate            | Network Outgoing Bandwidth   | Bit rate for outbound data from the Direct Connect side of a connection                                                         | >= 0 bits/s    | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: bit/s                                                                                                                     |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_incoming_bytes                | Network Incoming Traffic     | Number of bytes for inbound data to the Direct Connect side of a connection                                                     | >= 0 bytes     | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: byte                                                                                                                      |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_outgoing_bytes                | Network Outgoing Traffic     | Number of bytes for outbound data from the Direct Connect side of a connection                                                  | >= 0 bytes     | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: byte                                                                                                                      |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_incoming_packets_rate         | Network Incoming Packet Rate | Packet rate for inbound data to the Direct Connect side of a connection                                                         | >= 0 packets/s | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: Packet/s                                                                                                                  |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_outgoing_packets_rate         | Outgoing Packet Rate         | Packet rate for outbound data from the Direct Connect side of a connection                                                      | >= 0 packets/s | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: Packet/s                                                                                                                  |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_incoming_packets              | Network Incoming Packets     | Number of packets for inbound data to the Direct Connect side of a connection                                                   | >= 0 packets   | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: Packet                                                                                                                    |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_outgoing_packets              | Network Outgoing Packets     | Number of packets for outbound data from the Direct Connect side of a connection                                                | >= 0 packets   | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Unit: Packet                                                                                                                    |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | in_errors                             | Inbound Error Packets        | The number of inbound packets that could not be transmitted to the Direct Connect gateway over the connection because of errors | 0-2\ :sup:`32` | Connection       | 1 minute            |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_status                        | Port Status                  | The status of the port used by a connection                                                                                     | 0-DOWN         | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              |                                                                                                                                 | 1-UP           |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_incoming_discard_packets_rate | Inbound Packet Discard Rate  | The rate at which packets to the cloud over a Direct Connect connection are discarded                                           | >= 0 packets/s | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Packets may be discarded when the transmitted data exceeds the port bandwidth.                                                  |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+
   | network_outgoing_discard_packets_rate | Outbound Packet Discard Rate | The rate at which packets to the on-premises data center over a Direct Connect connection are discarded                         | >= 0 packets/s | Connection       | 1 minute            |
   |                                       |                              |                                                                                                                                 |                |                  |                     |
   |                                       |                              | Packets may be discarded when the transmitted data exceeds the port bandwidth.                                                  |                |                  |                     |
   +---------------------------------------+------------------------------+---------------------------------------------------------------------------------------------------------------------------------+----------------+------------------+---------------------+

Dimensions
----------

==================== =================
Key                  Value
==================== =================
direct_connect_id    Connection
virtual_interface_id Virtual interface
==================== =================
