<figure>
<img src="http://www.hypergrid.com/wp-content/themes/hypergrid/img/logo.png" alt="" />
</figure>

**Table of Contents**  

- [Registering Docker private and public repositories](#registering-docker-private-and-public-repositories)
- [Automating the building of Docker images](#automating-the-building-of-docker-images)

Registering Docker private and public repositories
----------

A user can register private or public repositories for Docker Registry, Docker Hub, Quay or Red Hat Container Registry. A user can use the newly registered repository in the following ways:
-   Push images to the repository using the Image Build feature.
-   Pull images from the repository as part of the Docker Compose template. The registry_id parameter will be needed to reference the registered repository.
-   Backup running containers by creating new images and pushing them into the registered repository. This can be done by click on the Actions menu for a running application and then selecting Backup.

To register a Docker repository, a user can navigate to **Cloud Providers** and then click on the **+New** button to select **Docker / Quay / Nexus / Artifactory**

The required fields are:
-   **Name** -- this is the name of the Docker Registry
-   **URL** -- this is the URL of the Docker Registry (e.g. for Docker Hub it's https://hub.docker.com/)
-   **Email** -- this is the email address used for the Docker registry
-   **Username** -- this is the username used for the Docker registry
-   **Password** -- this is the password for the Docker registry
-   **Entitled Users** -- these are the users who will be able to pull or push images to this registry. The entitled users do not have permission to manage or delete this registry. By default, the registry is marked as private. However, the registry owner can select specific users or groups.


Automating the building of Docker images
----------

If you have a Dockerfile in your code repository for building your latest images, then you can use HyperForm to automate the building of the Docker image as well as pushing the new images to one of the registered Docker registries.

Of course, if you're using Docker Hub, then you have the option to use the Automated Builds feature. However, if you're using a private registry, then HyperForm can provide the needed image build automation.

Once logged in to HyperForm (either the hosted DCHQ.io or on-premise version), a user can navigate to **Container Images** and then click on the **+New** button to create a new Dockerfile (Git/GitHub/BitBucket) image build.
Provide the required values as follows:
-   **Git URL** – (e.g. https://github.com/dchqinc/dchq-docker-php-example.git)
-   **Git Branch** – this field is optional -- but a user can specify a branch from a GitHub project. The default branch is master.
-   **Git Credentials** – a user can store the credentials to a private GitHub repository securely in HyperForm. This can be done by navigating to Cloud Providers and clicking on the + to select Credentials
-   **Cluster** – the building of Docker images is orchestrated through the HyperForm agent. As a result, a user needs to select a cluster on which an agent will be used to execute the building of Docker images. If a cluster has not been created yet, please refer to this section to either register already running hosts or automate the provisioning of new virtual infrastructure.
-   **Push to Registry** – a user can push the newly created image on either a public or private repository on Docker Hub or Quay. To register a Docker Hub or Quay account, a user should navigate to Cloud Providers and clicking on the + to select Docker Registries
-   **Repository** – this is the name of the repository on which the image will be pushed. For example, our image was pushed to dchq/php-example:latest
-   **Tag** – this is the tag name that you would like to give for the new image. The supported tag names in HyperForm include:
..***{{date}}** -- formatted date.
..***{{timestamp}}** -- the full time-stamp.
-   **Pre Build Plugins** - a user can select a plug-in that can be invoked before building the new image and pushing it to a registered registry
-   **Post Build Plugins** - a user can select a plug-in that can be invoked after building the new image and pushing it to a registered registry
-   **Build On Change** - a user can select this option to trigger an automated image build once a new commit is detected in the source control repository (e.g. GitHub or BitBucket)
-   **Cron Expression** – a user can schedule the building of Docker images using out-of-box cron expressions. This facilitates daily and nightly builds for users.
-   **Who can Manage** - a user can mark this build as private or share it with other users or groups.

Once the required fields are completed, a user can click **Save**.

A user can then click on the **Play** button to build the Docker image on-demand.
