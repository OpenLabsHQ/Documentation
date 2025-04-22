# Lab Structure

Welcome to OpenLabs! Our goal is to make designing, deploying, and managing network labs (especially for cybersecurity) straightforward and efficient. To get started, let's explore the core concepts that form the foundation of OpenLabs.

## Hierarchical Structure

OpenLabs organizes your lab environments using a clear, nested structure. Think of it like building with blocks, where larger blocks contain smaller ones. This hierarchy helps manage complexity and mirrors real-world network design principles.

1.  **Range:** This is the outermost container, representing your entire lab environment. It encompasses everything – all the networks and machines – deployed to a specific cloud provider (like AWS or Azure) and region.
2.  **VPC (Virtual Private Cloud):** Inside a Range, you have one or more VPCs. A VPC acts as your own private, isolated network in the cloud. It provides a dedicated IP address space, ensuring your lab network is separate from others.
3.  **Subnet:** Within each VPC, you can create multiple Subnets. A Subnet is a smaller segment or partition of your VPC's network. You might use subnets to separate different types of machines (e.g., web servers in one, database servers in another) or to create different security zones.
4.  **Host:** Finally, inside each Subnet, you have your Hosts. These are the individual virtual machines (VMs) – your servers, workstations, or target machines – running specific operating systems and applications.

**In short:** A `Range` holds `VPC(s)`, each `VPC` holds `Subnet(s)`, and each `Subnet` holds `Host(s)`. This structure provides organization and control over your lab's network layout.