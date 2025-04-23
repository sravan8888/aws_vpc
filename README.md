# aws_vpc
VPC stands for "virtuval private cloud"
VPC (Virtual Private Cloud) is like your own private network inside AWS. You use it to control your cloud resources securely, just like a traditional data center network.
The following diagram shows an example VPC. The VPC has one subnet in each of the Availability Zones in the Region, EC2 instances in each subnet, and an internet gateway to allow communication between the resources in your VPC and the internet.

You can decide:
What IP range your servers use (like 192.168.x.x).
Whether they connect to the internet or only stay private.
Which servers can talk to each other.
How to protect them using firewalls.
👉 Think of VPC like a secured house with different rooms (subnets), gates (internet gateway), guards (security groups), and rules (route tables) — all under your control.

Virtual private clouds (VPC)
A VPC is a virtual network that closely resembles a traditional network that you'd operate in your own data center. After you create a VPC, you can add subnets.

Difference: Manual CIDR vs IPAM CIDR
Feature    | IPv4 CIDR Manual Input        | IPAM-allocated IPv4 CIDR Block
Definition | You manually type an IP range | AWS allocates the IP from a pool managed by IPAM
Control    | You choose your range (e.g., 10.0.0.0/16) | AWS picks from your IPAM pool
When used  | Simple setups, single VPC     | Large orgs with many VPCs and central IP control
Overlapping risk | You manage it yourself  | IPAM prevents overlap across regions/accounts
Best for   | Learning, small projects      | Enterprises, multi-account architecture
Cost       | Free                          | IPAM might incur cost (depending on usage level)

When to Use What?
Scenario	Recommended CIDR Option
You are learning or doing personal projects	✅ Manual Input
You are managing a single or few VPCs	✅ Manual Input
You work in a large enterprise setup	✅ IPAM-allocated CIDR
You want centralized IP tracking & automation	✅ IPAM

Feature     | Manual Input               | IPAM-Allocated
Setup Speed | ✅ Fast                   | ❌ Slower (needs pool setup)
Ideal for   | Small setups, dev          | Large orgs, many VPCs
Auto CIDR Management | ❌ No            | ✅ Yes
Avoid IP Conflicts   | ❌ Manual effort | ✅ Automatic
Multi-region/Account Scaling | ❌ Hard  | ✅ Easy

Tenancy:
In AWS VPC (Virtual Private Cloud), tenancy refers to how EC2 instances are hosted on the underlying hardware. 
It mainly controls whether your instances share hardware with other AWS customers or use dedicated hardware.

Types of Tenancy in VPC:
Tenancy Type	Description
Default	Instances run on shared hardware. This is the most cost-effective option.
Dedicated	Instances run on dedicated hardware—that is, servers that are physically isolated for your use only.
Host	You get complete control over a physical server. You can launch instances on this host as you need.

 Real-Life Analogy: Hotel vs Private Villa
Think of EC2 instances like rooms where your applications live.

Tenancy Type	Analogy	Description
Default	Hotel Room	You rent a room in a hotel (shared building). Others also stay in the same hotel. It’s cheaper, but not private.
Dedicated	Private Floor in Hotel	You get an entire floor to yourself. Still in a hotel, but no other guests on your floor.
Host	Private Villa	You own the whole villa (physical server). You control how many rooms (instances) you want inside. Fully private and customizable.







