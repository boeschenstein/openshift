# OpenShift

## Login Error Red Hat: ERR_SSL_BAD_RECORD_MAC_ALERT

- try this: https://ugetfix.com/ask/how-to-fix-err_ssl_bad_record_mac_alert-error/
- try this: https://answers.microsoft.com/en-us/windows/forum/all/error-errsslbadrecordmacalert-and/8a6e2e58-a766-4666-a6b7-67d3771154ee
- I solved issue by using the wire instead of wireless

## Local OpenShift development environment on Windows: Install CodeReady Containers

>This will install Red Hat CodeReady Containers in Windows Hyper-V

- HowTo-Video: https://developers.redhat.com/openshift/local-openshift-windows
- Documentation: https://code-ready.github.io/crc/
- Download CodeReady Container (login to Red Hat) and pull secret

```powershell
cd C:\Users\bop\Downloads\crc-windows-amd64\crc-windows-1.13.0-amd64
$env:Path += ";C:\Users\bop\Downloads\crc-windows-amd64\crc-windows-1.13.0-amd64"

# setup help
crc setup -h

# setup
crc setup
```

reboot now

```powershell
# set path again, start setup again
$env:Path += ";C:\Users\bop\Downloads\crc-windows-amd64\crc-windows-1.13.0-amd64"
crc setup

# start help
crc start -h

# start
crc start -p C:\Users\bop\Downloads\pull-secret.txt

# set up environment
crc oc-env

# Login as admin (if needed)
oc login -u kubeadmin -p <snip> https://api.crc.testing:6443

# Login as developer
oc login -u developer -p developer https://api.crc.testing:6443

# Stop
crc stop

# Delete Container (BEWARE)
crc delete
```

## What's next

https://developers.redhat.com/openshift/
