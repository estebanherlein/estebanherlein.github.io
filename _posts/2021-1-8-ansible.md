---
title: "Ansible"
categories:
  - Blog
tags:
  - Dev-ops
  - Cloud Computing
---

Ansible is a free software platform for configuring and managing computers. 

It combines multi-node installation (ie: allows batch deployment of server and service configurations), ad hoc task executions, and configuration management. 

Additionally, Ansible is categorized as an orchestration tool. It manages nodes via SSH and does not require any additional remote software (except Python 2.4 or later3) to install it. It has modules that work on JSON and the standard output can be written in any language. It natively uses YAML to describe reusable system configurations.

<h2>Features</h2>

Ansible is generally grouped with other Configuration Management tools such as Puppet, Chef, 9, etc. 

<h3>Provisioning</h3>

With Ansible, you can provision the latest cloud platforms, virtualized hosts and hypervisors, network devices, and physical servers.

<h3>Configuration management</h3>

Establishes and maintains product performance by recording and updating information that describes a company's software and hardware. This information generally includes the versions and updates that have been applied to installed software packages and the locations and network addresses of the hardware devices.

<h3>Application deployment</h3>

When the application is defined with Ansible and its deployment is managed with Ansible Tower, it is possible to keep track of the entire life cycle of an application. From development to production.

<h3>Security and Compliance</h3>

Ansible makes it easy to define system security. Using the syntax of a Playbook, it is possible to define firewall rules, user and group management and personalized security policies in the systems that are being managed and you also have a large number of modules that help in the work.

<h3>Orchestration</h3>

Ansible is used to orchestrate OpenStack deployments for example. Companies such as Rackspace, CSC, HP, Cisco, and IBM trust Ansible to keep their OpenStack clouds available simply and securely.

<h2>Architecture</h2>

Like most configuration management software, Ansible distinguishes between two types of servers: controllers and nodes. First, there is a single control machine where the orchestration begins. The nodes are managed from that control machine by SSH. The control machine knows the nodes through an inventory.

To organize the nodes, Ansible deploys modules to the nodes the SSH protocol. The modules are temporarily stored in the nodes and communicate with the control machine through the JSON protocol on standard output. As Ansible does not control the modules since they are executed on the remote machine, they do not consume local resources because they do not there are processes or programs running in the background.

In contrast to other configuration control programs such as Chef and Puppet, Ansible uses an agentless architecture. With agent-based architecture, nodes must locally install a communication process that interacts with the control machine. 

With the agentless architecture the nodes do not need to install or run in the background any process that communicates with the control machine.

 This type of architecture reduces network overhead and prevents the use of more aggressive control strategies by the server (such as polling, with its constant query operations)

