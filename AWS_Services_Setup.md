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
The Amazon EC2 Service is designed to 
## Route53 ##
