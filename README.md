# deepstream-demo
DeepStream on Jetson AGX Xavier

Setup pre-requisites:
- Ubuntu 18.04
- NVIDIA DeepStream SDK 5.0 Developer Preview (download/install from https://developer.nvidia.com/deepstream-download)
- Python 3.6
- Gst-python
 
To install Gst-python:
- sudo apt-get install python-gi-dev
- export GST_LIBS="-lgstreamer-1.0 -lgobject-2.0 -lglib-2.0”
- export GST_CFLAGS="-pthread -I/usr/include/gstreamer-1.0 -I/usr/include/glib-2.0 -I/usr/lib/x86_64-linux-gnu/glib-2.0/include"
- git clone https://github.com/GStreamer/gst-python.git
- cd gst-python
- git checkout 1a8f48a
- ./autogen.sh PYTHON=python3
- ./configure PYTHON=python3
- make
- sudo make install

Download Python Sample Apps & Bindings:
developer.nvidia.com/python-sample-apps-bindings-v09

Extract Apps & Bindings:
- tar xf ds_pybind_v0.9.tbz2 -C <DeepStream ROOT>/sources

- cd <DeepStream ROOT>/sources/python/apps/deepstream-test3

Copy/overwrite this deepstream_test_3.py file into deepstream-test3.

Run:
- python3 deepstream_test_3.py file:/opt/nvidia/deepstream/deepstream/sources/python/apps/deepstream-test3/office.mp4 

Note: the uri has to be preceded by "file:" and the ABSOLUTE path to the video file.
