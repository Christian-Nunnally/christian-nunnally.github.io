# Visual Drop
Graphical, real-time, sound to light processing.

[Github](https://github.com/Christian-Nunnally/visual-drop)

The meat and potatoes of the project is currently split into two plugins. The names are not final. 
 * 'diiagramrfadecandy' is the visual side of things. Currently it wraps SharpDX for hardware accelerated graphics, and connects to [fcserver.exe](https://github.com/scanlime/fadecandy/tree/master/server) display the graphics on LEDs. 
 * 'visualdrop' is the audio side of things. Currently it depends on basswaspi.dll, bass.dll, and bassNET.dll to capture audio playing on your computer. After the audio data is captured, it does some DSP on that audio data, and them maps the live audio signals to effects.

*Notice: Diiagramr and Visual Drop are not finished. If you're interested in the project and might be interested contributing in some way feel free to reach out.*


# Videos
### Demo #1
<iframe width="560" height="315" src="https://www.youtube.com/embed/u6MFLxTwU9s" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Demo #2
<iframe width="560" height="315" src="https://www.youtube.com/embed/r4hIhaIN3ig" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Demo #3
<iframe width="560" height="315" src="https://www.youtube.com/embed/q0rIDTZ0bcU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### Installation Instructions (Windows 10)
Visual Drop is a set of plugins for Diiagramr that can be installed directly from inside the Diiagramr application.


#### Install Diiagramr
1. Download Diiagramr setup.exe from [https://diiagramr.blob.core.windows.net/diiagramrinstall/setup.exe](https://diiagramr.blob.core.windows.net/diiagramrinstall/setup.exe)
1. Run setup.exe **Windows smart screen will warn agaisnt running the application, this is because it is not a signed application. Proceed at your own risk**
1. Click 'Install' and Diiagramr should automatically download, install, and run


#### Install the plugins for Visual Drop
1. Open Diiagramr
1. From the `Tools` menu select `Tools`-> `Libraries` to open the Library Manager
1. Wait for the plugins list to load (this may take a while). In the Library Manager find 'diiagramrfadecandy'
1. Click install, which will automatically download and install the Visual Drop plugin into Diiagramr (this may take a while)
1. Restart Diiagramr.


# History **(WIP)**

#### The inspiration (Version 1.0)
It all started when I got a little [DIY color organ kit](https://www.jameco.com/jameco/products/prodds/2155541kitinstructions.pdf). No microprocessors, just good 'ol fashioned electronics. Here's a video:
<iframe width="560" height="315" src="https://www.youtube.com/embed/6ekGIv9uwj8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Version 2.0
MSGEQ7 & arduino uno & 3 x 1A LEDs
<iframe width="560" height="315" src="https://www.youtube.com/embed/G9CXwfTenjY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Version 3.0
Arduino uno (and code) & Bass.dll & 'ColorOrgan'

#### Version 4.0
Arduino duo (and code) & Bass.dll & 'ColorOrgan4'

#### Version 5.0
Arduino duo (and code) & Bass.dll & 'Diiagramr' + 'Visual Drop' plugin

#### Version 6.0
FadeCandy & Bass.dll & 'Diiagramr' + 'Visual Drop' plugin
