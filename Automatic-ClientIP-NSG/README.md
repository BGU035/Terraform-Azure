# Automating NSG rules with an external IP in Terraform

## Overview
This code dynamically creates an Azure Network Security Group (NSG) using Terraform. The NSG allows inbound RDP access from the Client IP of the machine running Terraform only. The IP address is gathered from an IP check service automatically. 

## Actions
This code creates a data source within Terraform, and then uses this during deployment, so that the NSG rule is created dynamically based on the Client IP. To do this, a data source is used, and a URL from an IP check service - see [azuredeploy.tf](azuredeploy.tf). In this example 3 things are carried out:

 - Creates a Resource Group to hold Resources
 - Checks the Client IP with https://ipv4.icanhazip.com/
 - Creates an NSG that allows inbound RDP using the IP from the IP Check Service above. 