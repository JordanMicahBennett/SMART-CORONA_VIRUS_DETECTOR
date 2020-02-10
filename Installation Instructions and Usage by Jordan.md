#Author: Jordan Bennett

#Notes: 
* Note that the original ViralMiner repo does not contain any installation instructions. 
* Python2.7 support died in January 2020, so lots of things are depracated, and setup took several hours. As a result:
	* I had to patch Python2.7 by doing small actions like copying/pasting dlls etc from place to place.
	* I also had to modify some of the ViralMiner code, before anything ran with 0 errors.
 
 
Patches and non-regular python installs
=========
1.	Download mingw-get-setup.exe. The link below is cited conveniently from a series of clicks: mingw.org ...Downloads...releases....MinGW Installation Manager (mingw-get) etc
	* https://osdn.net/projects/mingw/downloads/68260/mingw-get-setup.exe/

2.   Download and install last version of Python 2.7. (Important to avoid SSL errors, due to depracation wrt to modules required by ViralMiner)
	* https://www.python.org/downloads/release/python-279/
	
3.	From the site below, "libmsvcr90.a", and place in <C>:\Python27\Lib\. (Required to repair vcvarsall.bat related errors. Essentially allows python keras to do important C++ background stuff)
	* https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/host/x86_64-w64-mingw32-4.8/+/refs/heads/emu-2.2-release/x86_64-w64-mingw32/lib32
	
4.	Add mingw capability to <C>:\Python27\Lib\distutils\distutils.cfg, by adding the following lines:
		```
		[build]
		compiler=mingw32
		```

5.	Switch keras backend to "theano", which is Microsoft's cognitive toolkit in keras json config. (Found in <C>:/Users/<current-username>/.keras/keras.json:
		```
		{
				"epsilon": 1e-07, 
				"image_data_format": "channels_last", 
				"backend": "theano", /*Jordan_note: Alternative = "cntk", which requires Python 2.7.9 equivalent of CUDA 9.0.176, and cuDNN 7.0.5, along with NVidia drivers 384.111*/
				"device": "cpu",
				"floatx": "float32" 
		}
		```

6.	Download and Install VS2008ExpressENUX1397868.iso (Required to repair vcvarsall.bat related errors. Essentially allows python keras to do important C++ background stuff)
	* https://download.microsoft.com/download/8/B/5/8B5804AD-4990-40D0-A6AA-CE894CBBB3DC/VS2008ExpressENUX1397868.iso


	
Regular python installs (download each from PyPi)
=========

1 .	Download and Install cntk-2.7-cp27-cp27m-win_amd64.whl
2 .	Download and Install cntk_gpu-2.7-cp27-cp27m-win_amd64.whl
3 .	Download and Install distribute-0.6.35.tar.gz
4 .	Download and Install enum34-1.1.6.zip
5 .	Download and Install h5py-2.10.0-cp27-cp27m-win_amd64.whl
6 .	Download and Install h5py-2.10.0.tar.gz
7 .	Download and Install Keras-2.3.1.tar.gz
8 .	Download and Install Keras_Applications-1.0.6.tar.gz
9 .	Download and Install Keras_Preprocessing-1.1.0.tar.gz
10.	Download and Install nose-1.3.7.tar.gz
11.	Download and Install numpy-1.16.6.zip
12.	Download and Install matplotlib then install scikit_metrics
13.	Download and Install pip-20.0.2.tar.gz
14.	Download and Install pycuda-2019.1.2.tar.gz
15.	Download and Install python-dateutil-2.8.1.tar.gz
16.	Download and Install python_dateutil-2.8.1-py2.py3-none-any.whl
17.	Download and Install python_dev_tools-2020.2.5.tar.gz
18.	Download and Install pywin-0.3.1.zip
19.	Download and Install setuptools-45.0.0.zip
20.	Download and Install simple0-1.1.tar.gz
21.	Download and Install six-1.14.0.tar.gz
22.	Download and Install svn-1.0.1.tar.gz
23.	Download and Install Theano-1.0.4.tar.gz



Quick usage example
=========
