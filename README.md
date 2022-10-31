# deepstream-count-vehicles
Count vehicles that cross the line using nvtracker and nvdsanalytics plugins from deepstream in jetson nano 2Gb


demo links: 

https://youtu.be/MY3WNxhNDKY

https://youtu.be/_NH2Ern9-QI

https://youtu.be/Tx8CoeWUTV8

## Setup Steps

this project is built on top of the nvidia Building Video AI Applications at the Edge on Jetson Nano course.

You can connect to your jetson in headless device mode (ssh <username>@192.168.55.1) or by plaging a monitor, a keybord, a webcam and a mousse.

1) Add a data directory for the project with the following command in the Jetson Nano terminal you've logged into:
```
mkdir -p ~/my_apps
```
2) Run the Docker container with the following command for jetpack 4.6.1:
```
sudo docker run --runtime nvidia -it --rm --network host \
    -v /tmp/.X11-unix/:/tmp/.X11-unix \
    -v /tmp/argus_socket:/tmp/argus_socket \
    -v ~/my_apps:/dli/task/my_apps \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-deepstream:v2.0.0-DS6.0.1 
```
or the following command for jetpack 4.6.0:
```
sudo docker run --runtime nvidia -it --rm --network host \
    -v /tmp/.X11-unix/:/tmp/.X11-unix \
    -v /tmp/argus_socket:/tmp/argus_socket \
    -v ~/my_apps:/dli/task/my_apps \
    --device /dev/video0 \
    nvcr.io/nvidia/dli/dli-nano-deepstream:v2.0.0-DS6.0GA
```
you can check the full list in this link (https://catalog.ngc.nvidia.com/orgs/nvidia/teams/dli/containers/dli-nano-deepstream)

## Clone the project

1) Change directory to my_apps/
```
cd my_apps/
```
2) Clone this repo
```
https://github.com/MedAliMimouni/deepstream-count-vehicles.git
```

## Logging Into The JupyterLab Server

1) Open the following link address : 192.168.55.1:8888 in a new web browser window.
The JupyterLab server running on the Jetson Nano will open up with a login prompt the first time.

2) Enter the password: dlinano

You will see this screen.


![image](https://user-images.githubusercontent.com/9286366/198899346-8b4bdc7a-a4f2-4d76-899e-df087a59c10f.png)

Congratulations, you've finished the hardest part.


Now in my_apps/deepstream-count-vehicles open the jupyter notebook file setup_and_run.ipynb and run the cells to finish the rest of the instalation
