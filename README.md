*You can check the full estimate [here](https://github.com/fusaa/FishTank/blob/main/magic.pdf).*

# Summary

To migrate the PETRA application to AWS, it is recommended to take fully advantage
of services provided by the cloud. This is not only more cost effective but will lead to
performance and stability gains.  

The presented solution has been built using 2 different Availability Zones(AZs), this
will improve system availability and ensure continuous service for users.
It has been included two Auto Scaling groups, each paired with an Application Load
Balancer. The first for the Webserver virtual machines (EC2s) and the second to the
PETRA application EC2s. Considering the pay-as-you-go pricing model this can yield
to substantial savings over time. And in case the number of users grow, the system
can automatically start more EC2 instances avoiding this way a decrease in
performance.  

Microsoft SQL server can no longer be updated, which brings a series of issues with
security and lack of updates. So, in the presented project, the database platform is
being updated to Aurora, which provides states of art performance.  

The database will be also deployed in both AZ´s. In the first AZ it will operate as the
primary database, while in the second AZ it will be a replica. This will bring better
performance and redundancy in case the primary database becomes unavailable.
Finally, instead setting up a whole server for the Domain Controller we are making
use of the AWS Managed Microsoft AD service. This will make running the system
smoother, reducing the number of servers to be taken care of. This service will also
be activated using Multi-AZ Deployment, which translates to more system stability
and easier recover.  
