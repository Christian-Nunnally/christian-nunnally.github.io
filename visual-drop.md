# Visual Drop
Graphical, real-time, sound to light processing.

[Diiagramr on Github](https://github.com/Christian-Nunnally/Diiagramr)
[VisualDrop on Github](https://github.com/Christian-Nunnally/visual-drop)

The meat and potatoes of the project is currently split into two plugins. The names are not final. 
 * 'diiagramrfadecandy' is the visual side of things. Currently it wraps SharpDX for hardware accelerated graphics, and connects to [fcserver.exe](https://github.com/scanlime/fadecandy/tree/master/server) to display the graphics on LEDs. 
 * 'visualdrop' is the audio side of things. It uses the open source [CScore by filoe](https://github.com/filoe/cscore) audio processing library to capture audio playing on your computer. After the audio data is captured, it does some DSP on that audio data, and them maps the live audio signals to effects.

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

#### ~Install Diiagramr~ (Instructions outdated, if you're interested in this project contact me.)
1. ~Download Diiagramr setup.exe from [https://diiagramr.blob.core.windows.net/diiagramrinstall/setup.exe](https://diiagramr.blob.core.windows.net/diiagramrinstall/setup.exe)~
1. ~Run setup.exe **Windows smart screen will warn agaisnt running the application, this is because it is not a signed application. Proceed at your own risk**~
1. ~Click 'Install' and Diiagramr should automatically download, install, and run~

#### Install the plugins for Visual Drop
1. Open Diiagramr
1. From the `Tools` menu select `Tools`-> `Libraries` to open the Library Manager
1. Wait for the plugins list to load (this may take a while)
1. In the Library Manager find 'diiagramrfadecandy'
1. Click install, which will automatically download and install the Visual Drop plugin into Diiagramr (this may take a while)
1. In the Library Manager find 'visualdrop' install that too
1. Restart Diiagramr

#### Updating Diiagramr
Diiagramr will automatically check for updates when you open it. If there is a new update then Diiagramr will automatically download and install it before opening.

# History **(WIP)**

#### The inspiration (Version 1.0)
It all started when I got a little [DIY color organ kit](https://www.jameco.com/jameco/products/prodds/2155541kitinstructions.pdf). No microprocessors, just good 'ol fashioned electronics. Here's a video:
<iframe width="560" height="315" src="https://www.youtube.com/embed/6ekGIv9uwj8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Version 2.0
MSGEQ7 & arduino uno & 3 x 1A LEDs
<iframe width="560" height="315" src="https://www.youtube.com/embed/G9CXwfTenjY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Version 3.0
The processing speed of the Arduino Uno became a problem since I wanted to do everything in real-time. An Arduino can handle computing an FFT just fine, but trying to do more processing after the FFT was too much. To fix the limited speed of the Arduino, I decided to move the audio capture and processing into a C# application. I still relied on the Arduino to control the ws2812 LEDs I decided to use, so the C# application serially communicated the rendered video to the Arduino which was fast enough to read and display that data.

#### Version 4.0
The number of LEDs that I could control was very limited by the serial communication and clock speed of the Arduino Uno, so I upgraded to an Arduino Duo, and a enhanced the communication code with a small amount of frame compression. I also realized two requirements, I needed to be able to develop the algorithm I would use to convert sound to light incrementally, and I would need it to be very modular and adapt to when I needed to change what LEDs I'm using or where the music is coming from. The UI of the application was inspired by, and looked very much like a networking rack. Each part of the sound to light process was broken into modules that had inputs and outputs. You could then drag and drop them onto an array of virtual racks and then you would 'connect' the modules together by mapping the inputs and outputs by name.

#### Version 5.0
Mapping out the inputs and outputs turned out to be a pain, and I wanted a visual representation of the data flow just like I had visual feedback coming from the modules themselves so I landed on a node and diagram approach, with wires representing the data flow through the modules. Since the diagram editing was totally unrelated to the color organ (just a tool I needed for it), I decided to call it Diiagramr, and allow Diiagramr to load in 'plugins' that would provide the functionality for sound/light processing. I made sure that Diiagramr was a general purpose diagram execution shell so that I, or anyone else, could reuse it for other requirements.

#### Version 6.0
I found out about the Fadecandy and instantly realized how much I needed it for this project. Not having to deal with slow/buggy/fragile Arduino code would allow me to focus on what I originally wanted to do, make lights light up to the beat. Fadecandy also dramatically increases the number of LEDs that can be controlled with Visual Drop. I swapped out the simple pixel by pixel graphics code I was using for Direct2D support, allowing hardware accelerated rendering of some pretty fancy stuff. Finally, I swapped out the Bass.Net dependency with the open source [CScore](https://github.com/filoe/cscore) library so that I could distribute the project to the world and make it open source. Woohoo! Another win for free software.
