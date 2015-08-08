# CDH-Cluster-Install

## <center> Cloudera Manager Install
## <center> <a name="linux_config_check"/>Linux Configuration Check

This checklist uses a [presentation on Slideshare](http://tiny.cloudera.com/7steps) and is a small sample of an install precheck. 

1. Check swappiness on all your nodes, then set the recommended value
    * Set the value to 1 for current and future boots
2. Set <code>noatime</code> on DN volumes
    * For labs, do this on your root volume 
3. Set reserve space for root on DN volumes to 0
    * For labs, do this on your root volume
4. Check the user resource limits for max file descriptors and processes
5. Test forward and reverse lookups for both file-based and DNS name services
    a. Note: <code>/etc/hosts</code>, the [FQDN](https://en.wikipedia.org/wiki/Fully_qualified_domain_name) must be listed first  
    b. Note: <code>127.0.0.1</code> **must** resolve to <code>localhost</code>
6. Enable nscd
    a. Note: consult documentation before [running nscd with SSSD](http://goo.gl/68HTMQ)

---
<div style="page-break-after: always;"></div>
