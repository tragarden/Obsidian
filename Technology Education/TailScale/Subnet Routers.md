# Subnet Routers and TailScale

### Subnet Routers

A #Subnet #router acts as a gateway, which relays traffic from your #tailnet back onto your physically defined subnet.  These devices can be configured to respect  your access control policies.

#### Why?

For TailScale to work seamlessly, the best practice would be to install the TailScale client onto every device you want to include in your tailnet.  Sometimes devices will not permit the client to be installed and in cases where you are managing thousands of machines, using a subnet router would include all of these devices within the tailnet without installing the client. If you choose this method, you may need to manually configure devices that do not have the client installed. 

### Related:

- [TailScale Subnets](https://tailscale.com/kb/1019/subnets/ "What is a subnet?")
- [026 Security Best Practices](026%20Security%20Best%20Practices.md)
- [122 Network Devices](122%20Network%20Devices.md)
- [227 Network Types](227%20Network%20Types.md)