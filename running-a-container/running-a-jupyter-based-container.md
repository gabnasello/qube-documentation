# Running a Jupyter-based container

## Start the container

Let's start a `datascience` container, which runs a Jupyter Lab server

<figure><img src="../.gitbook/assets/bitmap (1).png" alt=""><figcaption></figcaption></figure>

You start a container by clicking **Start this stack**

<figure><img src="../.gitbook/assets/bitmap (2).png" alt=""><figcaption></figcaption></figure>

## Open the container link

**Open the container** created after starting the stack

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Scroll down to the **Container details**, copy the `CONTAINER_URL` and paste the link in a new page

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

And the container is ready-to-go!

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

## Access your data

You can [use-the-filebrowser-container.md](../transfer-data/use-the-filebrowser-container.md "mention") to load data inside the container.&#x20;

Data will be accessible at `/home/jovyan/researcher_home`

**IMPORTANT -** only files inside the `researcher_home` directory will be stored. The rest is deleted once you stop the container.
