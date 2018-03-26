# RedWhale – Multi Node DevStack on Docker

## RedWhale
<center>
<img src="http://i64.tinypic.com/2q9dp2r.jpg" alt="RedWhale logo">
</center>

Tool to deploy a multi node infrastructure of OpenStack using Docker technology. With RedWhale you can easly install, purge and manage an OpenStack infrastructure without corrupt your host system. In the end you can use RedWhale to deploy a distribuited infrastructure between more than one host. 
It creates a core image named "RedWhale-core" used to deploy a single controller node and multiple compute nodes.

## Objective
![scheme](http://i64.tinypic.com/dbqgwz.jpg "RedWhale Project")

Redwhale aims to simplify the deploy and the management of OpenStack and organize the infrastructure in multiple Docker containers, each for single node.  
Controller node is the main node able to control compute nodes.

## Requirements
* Linux distribution Debian based (tested on Ubuntu 16.04 LTS)
* 4 GB of RAM available for the infrastructure
* Docker (tested on 17.12.0-ce)

## Basic infrastructure
![scheme](http://i67.tinypic.com/24mujvp.png "RedWhale Scheme")

The basic infrastructure of RedWhale based on one Core image from which you can deploy multiple Controller and Computes nodes without wasting more space than needed thanks to the Docker technology.

## Usage

First of all you have to clone the repository and then build the Redwhale-core image:  
>$ ./redwhale --install  

This operation takes about 10/15 minutes.  
  
After core image is built, you can proceed to create controller node:  
>$ ./redwhale --add controller  

Now the system is ready to use (the controller node has nova module so you can create instances).

To add more compute nodes (provide names to specify different compute nodes):
>$ ./redwhale --add compute [name]

Controller creation takes about 30/40 minutes, while compute creation takes about 15/20 minutes.  

For futher details about RedWhale type:
>$ ./redwhale --help

## Supported modules
1. Nova [[1]]
2. Keystone [[2]]
3. Neutron [[3]]
4. Zun [[4]]
5. Horizon [[5]]
6. Glance [[6]]

## Supported nodes

## How to add more nodes and modules

## Authors

Salvatore Pizzimento [[8]]
Federico Fausto Santoro [[9]]

## Reference
RedWhale is meant to be created to provide an OpenStack infrastructure with Docker containers, but the original idea is from another GitHub user [[7]] 

[1]: https://docs.openstack.org/nova/latest/
[2]: https://docs.openstack.org/keystone/latest/
[3]: https://docs.openstack.org/neutron/latest/
[4]: https://docs.openstack.org/zun/latest/
[5]: https://docs.openstack.org/horizon/latest/
[6]: https://docs.openstack.org/glance/latest/
[7]: https://github.com/janmattfeld/DockStack
[8]: https://github.com/SalvoPizzimento
[9]: https://github.com/fedyfausto
