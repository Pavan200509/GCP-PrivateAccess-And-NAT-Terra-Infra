# GCP-PrivateAccess-And-NAT-Terra-Infra 

Lab - Configuring Private Google Access and NAT - GSP459

# Private Access -
VM's inside a VPC of a project can only access the VM's, LB, Network, and Subnet that are in same account, But cannot access directly the google managed services like big query, Spanner, Armor etc. As they are not part of google cloud Account.
A VM needs to have a Public IP(So VM through internet can access those services)/ Private Google Access which will create a secure connection with Internal Network known as google Backbone between resouces in GCP Account and google managed Services.
This Private Access is configured at Subnet level.

# NAT -
When a VM without public IP needs to download, update or fetch data from Internet then a NAT is required. As VM without Public IP cant access internet and also to maintian the security we use the NAT that will take the request from private serverand transfer the request into internet with some public IP assigned to it. It is only for Egress (BUt send back the response from internet to private VM which is requested by it).

# Bastion Host -
Even when a valid and authenticated source from internet want to access a Private VM in VPC it can't, Because there is no public IP for the VM to reach from internet and it is inside a secure VPC. So in this case we use the Bastion Host as it have a public IP which can be reached from internet. Bastion host acts as a single gateway for multiple Private VM's in a VPC. It uses SSH/RDP for windows to let source/user to login in to it and then login into private VM. Bastion is not only the source to reache Private VM, we can also use LB/ Identity Aware Proxy as alternatives.
 
# Network Interface (NIC) - 
A network Interface is configured when an every VM is configured, it acts as point of connection to a VM (In & Out). This NIC will store the details of vm like internal IP, External IP, Subnet Attachment, Firewalls configured at VPC level will be applied on this NIC's, NAT interaction Point.

# Diagram

# Components
Network,
Network Interface (NIC),
Firewall,
Subnet,
VM,
Bastion VM,
NAT,
Configure Private Access in Subnet

# Data Flow

# Authentication

# SS

# Key Learning
