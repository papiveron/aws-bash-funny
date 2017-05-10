# aws-bash-funny scripts

## RDS Preprod Provisionning

Here is a system built for provisionning a preprod/testing environment with a RDS instance and manage the RDS instance lifecycle.

The use case may be for example if you have to create an EC2instance and automatically associate a RDS instance to it for data base purpopses.

The RDS instance is cloned from a production RDS instance, and lives only with the preprod EC2 instance.

This means the RDS instance is created once and only once the EC2 instance is created/launch, and is automatically destroyed when the EC2 instance is terminated.

The process and mecanism to manage instances provisionning and lifecycle is up to the user, I just provide here the bash script with all necessay functions
 
The script first deletes the preprod rds if it exists, before creating it, and has four functions :

  * create_instance : create the rds instance from the last production snapshot
  * set_datas: updates databases, by making a dump / export of the prod databases and imports them in preprod rds
  * delete_insance : delete rds instance
  * reboot_intance: restart the rds instance
