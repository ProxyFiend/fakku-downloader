# Fakku Downloader
Ever wanted to save Fakku Unlimited manga to read offline? This is the solution for you. This script does not allow piracy, you must still pay for your subscription, but saves the manga to your hard drive for reading offline or on a device that doesn't support Fakku. (@apple)

### Usage
1) Download or clone this repo
2) Download the correct [Driver](https://selenium-python.readthedocs.io/installation.html#drivers) for your browser and put it in the root folder.
3) Rename the driver to "chromedriver.exe" (This is a temporary fix)
4) Install all python requirements by running **install.bat** or run <code>pip install -r requirements.txt</code>
5) Add all the URLs of each manga to urls.txt
6) Run download.bat or <code>py main.py</code>

### FAQ
#### Why not a browser extension?
That was the original plan. However it proved to be a monumental task. It turns out that each manga is stored as a scrambled image, and the Fakku reader unscrambles it then displays it on a canvas. If you were to download the image, it would be useless for reading. Unscrambling the image is near impossible thanks to how heavily the Fakku reader code is obfuscated. Finally the canvas it's rendered on doesn't allow javascript interaction for security reasons. This means outside of reverse engineering the Fakku reader, currently there is no way to download manga through a browser extension.

#### Why Python?
The original version of this script was already in Python. This fork is heavily modified, but it was better to stick with the same language than having to rewrite everything from scratch. Python also runs on all platforms, which is a helpful bonus.

## How to launch
1) Download or clone this repository
2) Download [ChromeDriver](https://chromedriver.chromium.org/downloads) the same version as you Chrome Browser and move it in root folder.
(Rename it to **chromedriver.exe**)
3) Create **urls.txt** file in root folder and write into that urls of manga one by line
4) Install all requirements for script via run **install.bat** (for Windows) or run <code>pip install -r requirements.txt</code>
5) Open root folder in command line and run the command <code>python main.py</code>

## Some features
* Use option -w for set wait time between loading the pages. If quality of .png is bad, or program somewhere crush its can help.
* Use option -t for set timeout for loading first page.
* Use option -l and -p for write the login and password from fakku.net
* More option technical you can find via --help

---
This section needs to be cleaned up.
## Working example

1. After downloading the repository, chromedriver and creating urls.txt file, root folder will be like this:
<p align="center">
	<img src="https://github.com/Witness-senpai/fakku-downloader/blob/master/readme_png/1.PNG" width="800">
</p>
2. Urls in urls.txt views like this:
<p align="center">
	<img src="https://github.com/Witness-senpai/fakku-downloader/blob/master/readme_png/2.PNG" width="800">
</p>
3. Write the command: python main.py
<p align="center">
	<img src="https://github.com/Witness-senpai/fakku-downloader/blob/master/readme_png/3.PNG" width="800">
</p>
4. If you launch program in first time, you need to login in opening browser and press enter in console. After that program save the cookies and will be use it in next runs in headless browser mode and skeep this step.
<p align="center">
	<img src="https://github.com/Witness-senpai/fakku-downloader/blob/master/readme_png/4.PNG" width="800">
</p>
5. Downloading process
<p align="center">
	<img src="https://github.com/Witness-senpai/fakku-downloader/blob/master/readme_png/5.PNG" width="800">
</p>
6. The program will create its own folder for each manga in urls.txt
<p align="center">
	<img src="https://github.com/Witness-senpai/fakku-downloader/blob/master/readme_png/6.PNG" width="800">
</p>
7. And inside in each folder you can see the manga pages in the most affordable quality as in a browser.
<p align="center">
	<img src="https://github.com/Witness-senpai/fakku-downloader/blob/master/readme_png/7.PNG" width="800">
</p>

## Extra: Download URLs from a Collection

If you have a collection that has the manga that you would like to download,
you can generate a **urls.txt** file that has all of its links.

Setup as above, and then call like this:

```bash
python main.py -z https://www.fakku.net/users/MY-USER-12345/collections/MY-COLLECTION
```

This will make a **urls.txt** file with the links, then run the program as normal
with this file as input.
