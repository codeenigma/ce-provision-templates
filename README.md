# ce-provision-templates
A collection of typical templates for infrastructure orchestrated with [ce-provision](https://github.com/codeenigma/ce-provision).

## WEB_SERVER_EC2
Template for creating a new standalone EC2 server.

The server.yml file is the 'main' play but this needs to copied to the infra repo and renamed as hostname.yml e.g. acme-dev1.yml.  You also need to copy provision.yml so you can control what is provisioned. The provision.yml file is intended only as a model.

If you want a separate RDS instance to pair with your EC2 instance then uncomment the last two play import lines in server.yml, however note you do need to sort out outbound firewall ports in iptables and a Security Group for inbound traffic to the RDS instance - usually port 3306 outbound from the EC2 instance in firewall_config and an SG that allows 3306 inbound to RDS.
