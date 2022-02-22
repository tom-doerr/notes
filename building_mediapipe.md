Steps to build python package with GPU support:
```
git clone --depth 1 git@github.com:google/mediapipe.git
cd mediapipe
```

In the file `setup.py`, replace all lines 
```
'--define=MEDIAPIPE_DISABLE_GPU=1',
```
with 
```
'--copt=-DMESA_EGL_NO_X11_HEADERS',
'--copt=-DEGL_NO_X11',   
```

Run
```
python3 setup.py gen_protos
python3 setup.py install --link-opencv
```
