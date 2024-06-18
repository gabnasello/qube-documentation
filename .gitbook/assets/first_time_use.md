# First time use?

* Install Visual Studio Code

Follow the [instructions](https://code.visualstudio.com/docs/remote/ssh) to install [Visual Studio Code](https://code.visualstudio.com/) and its [Remote-SSH extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)

* Connect to the BD Workstation

You need to be connected to KU Leuven Zone-A. The ssh command to login is the one below:

`ssh uxxxxxxx@gbw-d-l0151`

Where you have to insert your u/r number.

* Download the base BD directory from GitHub

After you successfully log in the first time, you need to download the directory with the docker-compose files you need to run the Docker contianers. To do that, run the command below:

`git clone https://github.com/gabnasello/BDcenter.git`

* Ask one of the administrators (Gabriele, Edo, Tim) to add you to the [`docker`](../admin\_notes/add\_user.md) group
