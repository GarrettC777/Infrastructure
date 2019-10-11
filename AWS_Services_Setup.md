# AWS Services #

## VPC ##
The Amazon VPC service is a virtual network that allows a user to launch other AWS resources within itself.

**1)** Our first step was to connect to the **Amazon VPC Console**, and navigate to the **Elastic IPs** link on the left side of the page.

**2)** We clicked on **Allocate New Address** and proceeded with creating a new Allocation ID which we would later use to create our VPC.

**3)** We then entered the **VPC Dashboard**, and clicked on **Start VPC Wizard**.

**4)** We went with the **VPC with Public and Private Subnets** option, and hit **Select*.

**5)** We filled out the required fields, and named the VPC **cit480**.

**6)** As required by the lab, we now had to create 2 additional public and private subnets. 

**7)** The current setup for both our public and private subnets are as follows:

	Public Subnet 1		10.0.16.0/20
	Public Subnet 2		10.0.32.0/20
	Public Subnet 3		10.0.48.0/20
	Private Subnet 1	10.0.0.0/22
	Private Subnet 2	10.0.4.0/22
	Private Subnet 3	10.0.8.0/22

**8)** Lastly, the **Route Tables** for the public and private subnets were automatically created, along with an **Internet Gateway**.
## EC2 ##
The Amazon EC2 Service is designed to make a secure compute capacity within AWS, allowing for easier web-scale computing.

**1)** We first navigated to the **Amazon EC2 Dashboard**, and chose **Launch Instance**.

**2)** Once given the option of which **AMI** to use, we chose to go with **Ubuntu 16.04**.

**3)** When prompted to choose **Instance Type**, we went with **t2.micro**.

**4)** We then focused on creating a cit480 **Security Group** with the given inbound and outbound settings:

**Inbound**

	Type			Protocol		Port Range		Source				Description
	HTTP			TCP			80			0.0.0.0/0			HTTP
	HTTP			TCP			80			::/0				HTTP
	All Traffic		All			All			142.129.57.191/32
	SSH			TCP			22			0.0.0.0/0			SSH
	SSH			TCP			22			::/0				SSH
	HTTPS			TCP			443			0.0.0.0/0			HTTPS
	HTTPS			TCP			443			::/0				HTTPS
	ICMP Rule		Echo Request		N/A			142.129.57.191/32

**Outbound**

	Type			Protocol		Port Range		Source				Description
	All Traffic		All			All			0.0.0.0/0

**5)** Finally, when hitting the **Launch** button, we are instructed to **Create a New Key Pair** which we then saved in a secure location.
## Route53 ##
The Amazon Route 53 Service is a high scalable cloud Domain Name System (DNS).

**1)** 
