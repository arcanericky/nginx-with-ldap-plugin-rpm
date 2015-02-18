#Nginx v1.6.2-1 w/ nginx-auth-ldap Plugin
RPM Source for Nginx with the nginx-auth-ldap plugin added. CentOS 7 was used for this source.

---

**NginxRPM source:** http://nginx.org/packages/centos/7/SRPMS/nginx-1.6.2-1.el7.ngx.src.rpm

**nginx-auth-ldap Source:** https://github.com/kvspb/nginx-auth-ldap, commit b365771d2a3d59ad464779f35e427fc665925477 at https://github.com/kvspb/nginx-auth-ldap/commit/b365771d2a3d59ad464779f35e427fc665925477

---

##Building

###Install RPM Utilities
```
$ yum groupinstall "Development Tools"
$ yum install fedora-packager
```

###Install Prerequisites
```
$ yum install pcre-devel openssl-devel
```

###Setup the `/rpmbuild Directory
Assuming this source was cloned into `~/nginx-with-ldap-plugin-rpm`
```
$ mv ~/nginx-with-ldap-plugin-rpm ~/rpmbuild
```
Or clone form this repository into `rpmbuild` directly
```
$ git clone https://github.com/arcanericky/nginx-with-ldap-plugin-rpm.git ~/rpmbuild
```

### Build
```
$ rpmbuild -ba ~/rpmbuild/SPECS/nginx.spec
```
Output will be at `~/rpmbuild/RPMS/x86_64/nginx-1.6.2-1.el7.centos.ngx.x86_64.rpm`

---
Thanks to https://www.tekovic.com/adding-custom-modules-to-nginx-rpm
