CAS Overlay Template
============================

Generic CAS WAR overlay to exercise the latest versions of CAS. This overlay could be freely used as a starting template for local CAS war overlays. The CAS services management overlay is available [here](https://github.com/Jasig/cas-services-management-overlay).

# Versions
```xml
<cas.version>5.0.0</cas.version>
```

# Requirements
* JDK 1.8+

# Configuration

The `etc` directory contains the configuration files and directories that need to be copied to `/etc/cas`.

Note that the `config` directory is expected to turn into a local `git` repository. 
To do so, execute the following commands:

```bash
cd /etc/cas/config
git init
```

# Build

```bash
./mvnw[.bat] clean package
```

# Deployment

## Embedded Tomcat

- Create a keystore file `thekeystore` under `/etc/cas`. Use the password `changeit` for both the keystore and the key/certificate entries.
- Ensure the keystore is loaded up with keys and certificates of the server.

Then, run:

```bash
java -jar target/cas.war
```

CAS will be available at:

* `http://cas.server.name:8080/cas`
* `https://cas.server.name:8443/cas`

## External
Deploy resultant `target/cas.war`  to a servlet container of choice.
