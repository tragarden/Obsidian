# DNS Zones

### Primary DNS Server

The Primary DNS server holds the zone file containing all authoritative information for the domain. The DNS records stored here can only be modified by the primary DNS server that passes this information to secondary DNS servers.

### Secondary DNS Server

The Secondary DNS server contains read-only copies of the primary DNS server's zone files. The compare the data they contain to the primary DNS server to ensure integrity and effectively work as a backup to the primary servers.

### Zone Files

There are primary and secondary zone files (formerly known as master and slave zones) that function the same as the primary and secondary DNS servers. When these files are copied between the two servers, this is known as 'Zone Transfer'.

There are two types of zone transfers:

- #AXFR - Asynchronous Full Transfer Zone - transfers all zone file entries.
- #IXFR - Incremental Zone Transfer - transfers only changed or new file entries.

### Considerations

A potential problem with the servers and zone files is that they can be requested by any client and do not require authentication. Any client could theoretically view all contents of all zone files. This could lead to discovered attack vectors as even in modern times it is common for these servers to be misconfigured, allowing threat actors to exploit them.

