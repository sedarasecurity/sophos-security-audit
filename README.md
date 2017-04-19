sophos-security-audit
=================

AlienVault plugin for Sophos Enterprise Console

# Installation
## Download the plugin
This should be ran on the Server, AIO or Sensor where you want to capture the Sophos logs from.

```
wget https://raw.githubusercontent.com/sedarasecurity/sophos-security-audit/master/sophos-security-audit.cfg -O /etc/ossim/agent/plugins/sophos-security-audit.cfg
```

## Import the plugin SIDs
This should be ran on the Server or AIO.

```
wget https://raw.githubusercontent.com/sedarasecurity/sophos-security-audit/master/sophos-security-audit.sql -O /tmp/sophos-security-audit.sql
ossim-db < /tmp/sophos-security-audit.sql
rm -f /tmp/sophos-security-audit.sql
```


## Install and configure dbpoller
You will need to already have a copy of dbpoller available to you.

```
mkdir -p /opt/sedara/{conf,bin,state}
wget https://raw.githubusercontent.com/sedarasecurity/sophos-security-audit/master/dbpoller/dbpoller-sophos-security-audit.toml -O /opt/sedara/conf/dbpoller-sophos-security-audit.toml
```

Edit /opt/sedara/conf/dbpoller-sophos-security-audit.toml and update any values of __changeme__ to the ones for your environment

