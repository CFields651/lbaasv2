# lbaasv2
The documentation for Red Hat OpenStack Platform 10 is not very accurate for installing lbaasv2:

https://access.redhat.com/documentation/en-us/red_hat_openstack_platform/10/html/networking_guide/sec-lbaas    

This kbase is closer, but the correction the author identified is no longer needed in the current release:  

https://access.redhat.com/solutions/2837871  

The code in this repo should work for:  

$ rpm -qi openstack-neutron-lbaas  
Name        : openstack-neutron-lbaas  
Epoch       : 1  
Version     : 9.1.0  
Release     : 4.el7ost  

This presumes that the haproxy service is installed and running.  

When you start the neutron-server servive it logs this warning:  
WARNING stevedore.named [-] Could not load neutron_lbaas.drivers.haproxy.plugin_driver.HaproxyOnHostPluginDriver   

When you start the neutron-lbaasv2-agent it logs these warnings:  
WARNING stevedore.named Could not load neutron.agent.linux.interface.OVSInterfaceDriver  
WARNING stevedore.named Could not load neutron_lbaas.drivers.haproxy.namespace_driver.HaproxyNSDriver  

Despite the warnings, the load balancer seem to work.  Here are good instructions:  
https://docs.openstack.org/ocata/networking-guide/config-lbaas.html  


