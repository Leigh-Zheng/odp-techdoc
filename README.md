
# TechDoc on GCP (Demo only)

This repo is for hosting technical documentation static pages in GCP appengine. This implementation uses GCP app engine for hosting static pages, GCP IAP proxy for authentication, GCP cloud build ci/cd, Github for storing code and static page content, huho with docsy theme to build static pages. This is based on hugo docsy theme similar to [kubernates.io](https://kubernetes.io/).

Follow steps below to duplicate this implementation to host your own static webpage. 

1. Fork this repo in [github] (https://github.com)

2. Request or create GCP project:

     You will atleast need editor or owner level permission to be able to enable API or support to enable API and required permission for different service account. 

3. Bootstrap GCP project:

     Bootstrap GCP project. Enable APP engine API, enable cloud build API, Enable IAP, create oauth concent, enable cloud storage. 

4. Sync your repo with [google cloud source repository](https://source.cloud.google.com/)

     This is extra step needed due to existing issue with cloud build not being able to download and sync git sub-modules used by docsy these. Update below valiable in cloudbuild.yaml file to match your mirred repo name

     _MIRROR_CLOUD_REPO: "github_USERNAME_techdoc"

5. Build trigger and link to your repo

     Build google cloud build trigger which will use cloudbuild.yaml file to trigger build when code in committed in your brach of choice. Ensure that cloud build service account "PROJECT_NUMBER]@cloudbuild.gserviceaccount.com " have a "App Engine Deployer",  "Service Account User" &  "App Engine Service Admin role". Please co role permission from IAM. 

6. Configure Identity Aware proxy to enforce authentication for GSA internal users or users from specific groups

7. Create app engine firewall rules (as needed)

8. Update config.toml file

9. Update your homepage and documents

10. Verify custum domain names, create cname record for your apppengine url to use your own domain url like example.com


## To Do

* Clean up
* Better doc
* Cloud schedular to trigger rebuild every week, to get updated images for app engine
* Use alphine image for hugo (update hugo docker file)







## Reference 

[Docsy](https://github.com/google/docsy) is a Hugo theme for technical documentation sites, providing easy site navigation, structure, and more. This **Docsy Example Project** uses the Docsy theme, as well as providing a skeleton documentation structure for you to use. You can either copy this project and edit it with your own content, or use the theme in your projects like any other [Hugo theme](https://gohugo.io/themes/installing-and-using-themes/).

This Docsy Example Project is hosted at [https://example.docsy.dev/](https://example.docsy.dev/).

You can find detailed theme instructions in the Docsy user guide: https://docsy.dev/docs/

This is not an officially supported Google product. 