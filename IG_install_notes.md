Notebook on installations

```rb
  conda create -n cvd pip python==3.8
  pip install ig_requirements.txt
```
NB. I had to resolve a lot of dependency conflicts to get this to install, and loosen several package reqs by editing the requirements file.

Installed on JADE2 (linux)

You may have to do the below on JADE to get pip to look at the right place (your conda install)

* Set PYTHONNOUSERSITE to avoid conflicts with user packages. Do this with your conda environment not active.
```rb 
export PYTHONNOUSERSITE=1
```

Full list of req changes:

1. Removed or loosened version constraints:
   - audioread: Changed from "==3.0.0" to no version specified
   - certifi: Removed version constraint
   - gast: Changed from "==0.4.0" to "==0.5.3"
   - google-auth: Removed version constraint
   - grpcio and grpcio-status: Removed version constraints
   - OpenCC: Removed version constraint
   - protobuf: Changed from no version to "==3.19.6"
   - PyQt5, PyQt5-Qt5, PyQt5-sip, PyQtWebEngine, PyQtWebEngine-Qt5: Removed version constraints
   - PyYAML: Changed from no version to "==6.0"
   - requests: Changed from no version to "==2.28.2"
   - tensorboard, tensorboard-data-server: Removed version constraints
   - tensorflow: Changed from no version to "==2.11.0"
   - torch: Changed from "==1.13.1" to "==2.0.0"
   - torchaudio: Changed from "==0.13.1" to "==2.0.0"
   - torchvision: Changed from "==0.2.2" to "==0.15.1"

2. Added packages (some of these were listed as local installs on the repo pip_requirements.txt:
   - google-api-core==2.11.0
   - google-api-python-client==2.83.0
   - google-cloud-texttospeech==2.14.1
   - googleapis-common-protos==1.58.0
   - mkl-fft==1.3.1
   - mkl-service==2.4.0
   - onnx==1.12.0
   - yellowbrick==1.5

3. Removed packages:
   - pysptk (was version 1.0.1)
