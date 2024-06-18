# Running a Jupyter-based container

## Start the container

Let's start a `datascience` container, which runs a Jupyter Lab server

<figure><img src="../.gitbook/assets/bitmap (1).png" alt=""><figcaption></figcaption></figure>

You start a container by clicking **Start this stack**

<figure><img src="../.gitbook/assets/bitmap (2).png" alt=""><figcaption></figcaption></figure>

## Get the Jupyter token

Before you open the container, **copy the Jupyter token** from the `container logs` that you access from **Quick Actions**

<figure><img src="../.gitbook/assets/bitmap (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## Open the published port

Once the token is copied, you can go back to the main page of the stack you started and open the published port dedicated to your container

<figure><img src="../.gitbook/assets/bitmap (4).png" alt=""><figcaption></figcaption></figure>

You will be redirected to a Jupuyter Notebook interface where you will have to past your token

<figure><img src="../.gitbook/assets/bitmap (5).png" alt=""><figcaption></figcaption></figure>

## Access your data

You can [use-the-filebrowser-container.md](../transfer-data/use-the-filebrowser-container.md "mention") to load data inside the container.&#x20;

Data will be accessible at `/home/jovyan/researcher_home`

**IMPORTANT -** only files inside the `researcher_home` directory will be stored. The rest is deleted once you stop the container.
