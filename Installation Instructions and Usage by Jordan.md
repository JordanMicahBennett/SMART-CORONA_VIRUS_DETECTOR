Author: Jordan Bennett
=========

This pertains to [Project - Smart Coronavirus Detector](https://github.com/JordanMicahBennett/SMART-CORONA_VIRUS_DETECTOR/blob/master/README.md).


Notes: 
=========
* Note that the original [ViralMiner](https://github.com/NeuroCSUT/ViraMiner) repo does not contain any installation instructions, and [ViralMiner](https://github.com/NeuroCSUT/ViraMiner) is based on the depracted Python 2.7, where I did somewhat unorthodox patching etc  to get things running, and so I created a set of instructions here.

* Python2.7 support (that the [ViralMiner](https://github.com/NeuroCSUT/ViraMiner) repo is written in) [died in January 2020](https://pythonclock.org/), so lots of things are depracated, and setup took several hours. As a result:
	* I had to patch Python2.7 by doing small actions like copying/pasting dlls etc from place to place.
	* I also had to modify some of the ViralMiner code, before anything ran with 0 errors.
 
* Using [ViralMiner](https://github.com/NeuroCSUT/ViraMiner)'s already pretrained models wrt genome deep learning, may be worth the resulting efficiency gained in genome analysis and identification in human samples, related to nCov coronavirus 2019 genome datasets released via China seen below in the "DATA" section.


 
Patches and non-regular python installs
=========
1.	Download mingw-get-setup.exe. The link below is cited conveniently from a series of clicks: mingw.org ...Downloads...releases....MinGW Installation Manager (mingw-get) etc

	* Note, in mingw manager below, achieved after a few clicks starting at mingw-get-setup.exe, select "MSYS Base System".
	
	* Ensure the installation is in your root directory, like C:/.
	
	* https://osdn.net/projects/mingw/downloads/68260/mingw-get-setup.exe/

2.   Download and install last version of Python 2.7. (Important to avoid SSL errors, due to depracation wrt to modules required by ViralMiner)
	
	* https://www.python.org/downloads/release/python-279/
	
3.	From the site below, "libmsvcr90.a", and place in <C>:\Python27\Lib\. (Required to repair vcvarsall.bat related errors. Essentially allows python keras to do important C++ background stuff)
	*  https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/host/x86_64-w64-mingw32-4.8/+/refs/heads/emu-2.2-release/x86_64-w64-mingw32/lib32
	
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


7. Replicate this modification of mine of the original repository:
	* This is a replacement of the "def wc ():" function, used in the line "test_set_size = wc(args.input_file)".
	
	* Add the following code, then modify the line above to invoke wc2 instead of wc. Wc uses depracated subprocess method to find out information about input file dataset. This information is a count of the test data, and is needed for the machine learning algorithm to work.
	```
		def wc2(filename):
			c = 0
			with open(filename) as file:
				while True:
					chunk = file.read(10 ** 7)
					if chunk == "":
						return c
					c += chunk.count("\n")
	```
	
	
	
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

1. Run cmd.

2. Set path by the following; beyond the typical python path, mingw and visual studio msvcr90.dll paths have been added to resolve vcvarsall.bat related errors 
	* Note: Adjust according to your Visual Studio 9, Python27 and MingW root based directories.
		* Where  Visual Studio 9 = VS2008ExpressENUX1397868.iso from step 6 in "**Patches and non-regular python installs**".
	
	* "PATH=C:/Python27/;C:/MinGW/bin;C:/Program Files (x86)/Microsoft Visual Studio 9.0/VC/redist/Debug_NonRedist/x86/Microsoft.VC90.DebugCRT"
	
3. Finally, use command from original repo, this example is a command I prepared based on the repo:
	* It should work if you had first navigated to the repo directory. The command runs on test data of genome sequence information in fullset_test.csv as well as the optimal pretrained models in the repository.
	
	* Command: **python predict_only.py --input_file data/DNA_data/fullset_test.csv --model_path final_ViraMiner/best_ViraMiner_end2end.hdf5 > output_preds.txt**
	
4. A succeful setup means that you see the following step, with a few warnings, and 0 errors:
	
