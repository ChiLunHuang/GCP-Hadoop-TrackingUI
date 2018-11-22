# GCP-Hadoop-TrackingUI
The way to use TrackingUI of Google Cloud Platform (for Mac OS X)

## Follow the steps from google pages
>https://cloud.google.com/sdk/docs/quickstart-mac-os-x

**1. Check version of python (Python 2.7)**

` python -V`

**2. Download the archive file:**

Mac OS X (x86_64) or Mac OS X (x86)

**3. Install :**

`./google-cloud-sdk/install.sh`

**4. init :**

`gcloud init`

**5. Build ssh to the cluster :**

```bash 
gcloud compute ssh  --zone=<zone> --ssh-flag="-D 1080" --ssh-flag="-N" --ssh-flag="-n" <ClusterName-m>
```

**6. Start a web page:**

```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --proxy-server="socks5://localhost:1080" --host-resolver-rules="MAP * 0.0.0.0 , EXCLUDE localhost" --user-data-dir=/tmp/<ClusterName-m>
```
**7. View TrackingUI or Jupyter :**

TrackingUI: `http://<ClusterName-m>:8088`

Jupyter: `http://<ClusterName-m>:8123`
