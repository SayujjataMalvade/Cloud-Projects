# Amazon EC2 (Elastic Compute Cloud)

Amazon EC2 (Elastic Compute Cloud) allows you to deploy and manage virtual servers in AWS using AMIs (Amazon Machine Images). AMIs act as templates containing the operating system, configurations, and software packages required for launching your instance.

EC2 provides:

* Flexible compute capacity

* On-demand provisioning

* Various instance types for different workloads

* Secure networking and storage options

# 🔐 Security Groups

A Security Group (SG) is a virtual firewall applied at the EC2 instance level (ENI — Elastic Network Interface).
It controls inbound and outbound traffic using rules based on ports, protocols, and IP ranges.

Key Points:

* Stateful firewall

* Denies all traffic by default

* Must explicitly allow the required ports

* Operates at the instance level, not network level

# 🔑 Key Pairs

Key pairs are:

* Region-specific

* Stored in your local machine

* Used to securely authenticate (SSH/RDP) into your instance

* Must be used within 4 minutes of instance launch to ensure successful login

# 💾 Storage Types in EC2

EC2 provides two primary storage options:

1. Instance Store

* Temporary storage attached physically to the host machine

* Data is lost if the instance is:

* Stopped

* Terminated

* Rebooted

* Best for cache, buffer, or temporary data storage

* Cost-effective but not durable

2. Amazon EBS (Elastic Block Store)

* Persistent block storage that retains data even after:

* Stop

* Reboot

* Can be detached and attached to other EC2 instances


  Ideal for:

* Databases

* Application data

* Logs

* More expensive compared to Instance Store, but highly reliable

# 🌐 Elastic IP (EIP)

An Elastic IP is a static, public IPv4 address that you can associate with any EC2 instance.
It is mainly used for:

  * Dynamic routing

  * Ensuring your server remains reachable even if the underlying instance changes

  * In short: Elastic IP = Permanent public IP in AWS

They help ensure secure, encrypted access to your server.

# ⚙️ Scaling EC2 Instances

EC2 supports efficient scaling using:

* Load Balancers (ELB) → Distribute incoming traffic across instances

* Auto Scaling Groups (ASG) → Automatically increase or decrease EC2 count based on demand

  This ensures:

 * High availability

 * Cost optimization

 * Application reliability
