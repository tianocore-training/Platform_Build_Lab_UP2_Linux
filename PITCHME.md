---?image=assets/images/gitpitch-audience.jpg
@title[Platform Build Win Lab]
<br><br>
<span style="font-size:0.75em" >This slide deck has moved to:  https://gitpitch.com/tianocore-training/Platform_Build_Lab_UP2_Linux/master#/</span>
<br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### Platform Build for UP Squared Linux Lab 

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  Platform Build Lab UP2 Linux

  Copyright (c) 2019, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.



---  
@title[Lesson Objective]

### <p align="center"<span class="gold"   >Platform Build Labs </span></p>
<br>
<br>
<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
 @fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Hardware Setup for UP Squared  </span><br><br>
 @fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Build a EDK II Platform using UP Squared  </span> <br><br>
  
---?image=assets/images/binary-strings-black2.jpg
@title[Setup UP2 HW Section]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Platform HW Setup</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Setup hardware for the Broxton - UP Squared </span>

---?image=/assets/images/slides/Slide4.JPG
@title[UP2 HW]
### <p align="right"><span class="gold" >EDK II Platform (UP Squared)</span></p>
@snap[south-west span-45 ]
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.56em" >Intel<sup>&reg;</sup> Celeron<sup>tm</sup> processor N3350 Series<br> &lpar;Formerly Apollo Lake&rpar;</span></p>

@snapend


@snap[south-east span-45 ]
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.56em" >
Available from <a href="https://www.aaeon.com/">Aaeon </a> <br> order at: <a href="https://up-shop.org/up-boards/92-up-squared-celeron-duo-core-2gb-memory32gb-emmc.html">here </a>
</span></p>
@snapend

Note:

This lab shows the build process for an actual platform – UP Squared
https://www.google.com/imgres?imgurl=https%3A%2F%2Fksr-ugc.imgix.net%2Fassets%2F014%2F192%2F390%2Fb48b13570b839fdb254d046a4e5fe703_original.png%3Fixlib%3Drb-1.1.0%26crop%3Dfaces%26w%3D1552%26h%3D873%26fit%3Dcrop%26v%3D1479219233%26auto%3Dformat%26frame%3D1%26q%3D92%26s%3Dd8c8e37c0ed5f65b97557dd77e441059&imgrefurl=https%3A%2F%2Fwww.kickstarter.com%2Fprojects%2F802007522%2Fup-squared-the-first-maker-board-with-intel-apollo&docid=hdDbuF0mF4AVzM&tbnid=rQVd58-OYexfgM%3A&vet=10ahUKEwjb-uLy_JDgAhUKsFQKHUnbC7wQMwhCKAIwAg..i&w=1552&h=873&bih=851&biw=1378&q=up%20squared&ved=0ahUKEwjb-uLy_JDgAhUKsFQKHUnbC7wQMwhCKAIwAg&iact=mrc&uact=8



Using Tianocore source
Open source EDK II plus open source binary obj. packages


This lab shows the build process for an actual platform – UP Squared

- Using Tianocore source
- Open source EDK II plus open source binary obj. packages

---?image=/assets/images/slides/Slide5.JPG
@title[Workshop Lab Hardware]
### <p align="right"><span class="gold" >UP Squared Workshop Lab Hardware</span></p>
@snap[south span-100 ]
<br>
<p style="line-height:80%" ><span style="background-color: #FFFFFF; font-size:0.60em; "> <font color="red">&nbsp;<b>**Warning</b> do not use any other power supply than 5V or the board will Fry&nbsp;&nbsp;</font></span></p>
<br>
@snapend
Note:

**Warning do not use any other power supply than 5V or the board will Fry


---?image=/assets/images/slides/Slide6.JPG
@title[Install Ubuntu “Screen”]
### <p align="right"><span class="gold" >Install Ubuntu “Screen”</span></p>

@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%" align="left"><span style="font-size:0.80em;  " >
 Terminal prompt (Cnt-Alt-T)<br>
 Install "Screen"
 <br>
 <br>
 <font face="Consolas"><span style="background-color: #000000; font-size:0.650em;"> 
&nbsp;&nbsp; bash$ sudo apt-get install screen &nbsp;&nbsp;<br>
&nbsp;&nbsp; bash$ cd $Home &nbsp;&nbsp;<br>
&nbsp;&nbsp; bash$ gedit ~.screenrc &nbsp;&nbsp;
</span></font><br><br>
Inside the editor, type<br> @size[.8em]("`shell /bin/bash`") &nbsp;&nbsp;then save
</span></p>
<br>
@snapend

@snap[north-east span-45 ]
<br>
<br>
<p style="line-height:70%" align="left"><span style="font-size:0.60em;  " >
 <font color="#87E2A9"> While in screen<br>
 <b>Cnt-A</b> then <b>D</b> goes back to Terminal
 <br></font><br>
 @size[.9em](`bash$ screen -r`) <br>
 (Returns to screen)
</span></p>
 <br>
@snapend



@snap[south-east span-80 ]
<p style="line-height:70%" align="left"><span style="font-size:0.60em;  " >
There may be other serial terminal applications that are supported. <br>
</span></p>
@snapend

Note:
- Terminal prompt (Cnt-Alt-T)<br>
`bash$ sudo apt-get install screen`<br>
`bash$ cd $Home`<br>
`bash$ gedit ~.screenrc`


` shell /bin/bash`

Click Save



---?image=/assets/images/slides/Slide7.JPG
@title[Setup UP2 Test System]
<p style="line-height:85%" align="right"><span class="gold" >@size[1.1em](<b>Setup UP Squared Test System</b>)</span></p>
@snap[north-west span-60 ]
<br>
<br>
<p style="line-height:50%"><span style="font-size:0.7em"><b>Hardware:</b></span></p>
<ul style="list-style-type:none; line-height:0.5;">
  <li><span style="font-size:0.5em">- System Under Test (SUT) - UP Squared  </span>  </li>
  <li><span style="font-size:0.5em">- FTDI USB to 3.3V TTL Cable  (6 pin) </span>  </li>
  <li><span style="font-size:0.5em">- USB / EP-CBUSB10PFL01  (3 pin & 10 pin) </span>  </li>
 <li><span style="font-size:0.5em">- 5V  6 amp power supply </span>  </li>
 <li><span style="font-size:0.5em">- 3 jumper wires (black, red, white) </span>  </li>
</ul>


<p style="line-height:50%"><span style="font-size:0.6em">
Connect the USB 10 pin header to SUT  <br><br>
Connect the FTDI USB w/ 6 pin to 3 pin connector using jumper wires <br><br>
Connect the FTDI USB Type A connector to Host (Laptop) </span> </p>
@snapend

Note:

- Hardware:
  - System Under Test (SUT) – UP Squared
  - USB to 3.3V TTL Cable  (6 pin to USB Type A)
  -  5V power supply

- Connect the USB w/ 6 pin header to SUT 3 pin connected to (UP Squared) via 10 Pin connected using jumper wires (black, red, white)

- Connect the USB Type A connector to Host (Laptop)

---?image=/assets/images/slides/Slide8.JPG
@title[UP Squared Test System 02]
### <p align="right"><span class="gold" >Setup UP Squared Test System</span></p>
@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%" align="left"><span style="font-size:0.80em;  " >
 Open Terminal prompt (Cnt-Alt-T)<br>
 <br>
 <font face="Consolas"><span style="background-color: #000000; font-size:0.60em;"> 
&nbsp;&nbsp; bash$ dmesg &nbsp;&nbsp;<br>
&nbsp;&nbsp; bash$ sudo chmod 666 /dev/ttyUSB@color[cyan](<i>n</i>) &nbsp;&nbsp;
</span></font>
</span></p>
<br>
@snapend

@snap[north-east span-55 ]
<br>
<br>
<p style="line-height:70%" align="left"><span style="font-size:0.60em;  " >
 <br>
 <br>
 (to check which USB port is assigned)<br>
 (where @color[cyan](<i>n</i>) is the FTDI number ) &nbsp;&nbsp;
</span></p>
<br>
@snapend

Note:

- Open Terminal Prompt (Cnt-Alt-T)
```
bash$ dmesg                     	#(to check which USB port is assigned)
bash$ sudo chmod 666 /dev/ttyUSBn	#(where n is the FTDI number)
```
- dmesg command  shows which - ttyUSBn




---?image=/assets/images/slides/Slide9.JPG
@title[Power on UP Squared]
<p style="line-height:80%" align="right"><span class="gold" >@size[1.1em](<b>Power on UP Squared</b>)</span></p>
@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:80%" align="left"><span style="font-size:0.80em;  " >
 Connect the Power supply cable to the UP Squared <br>
 <font face="Consolas"><span style="background-color: #000000; font-size:0.650em;"> 
&nbsp;&nbsp; bash$ screen /dev/ttyUSB@color[cyan](<i>n</i>) 115200 &nbsp;&nbsp;
</span></font><br>
UP Squared should boot to the UEFI Shell in the Terminal – Screen
</span></p>
<br>
@snapend

@snap[north-east span-25 ]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:80%" align="left"><span style="font-size:0.560em;  " >
 <br>
 <br>
 @color[yellow](While in Screen<br> <b>Cnt-A</b> then <b>D</b> goes back to terminal.)<br>
 <br>
 <font face="Consolas"><span style="background-color: #000000; font-size:0.90em;"> 
&nbsp;&nbsp; bash$ screen-r &nbsp;&nbsp;
</span></font><br> 
(returns to Screen)
  &nbsp;&nbsp;
</span></p>
<br>
@snapend




Note:
- Connect the Power supply cable to the UP Squared
```
bash$ screen /dev/ttyUSBn 115200
```
- UP Squared should boot to the UEFI Shell in the Terminal – Screen .

- While in screen  Cnt-A then D goes back to terminal
```
 bash$ screen –r #(returns to screen)
```
- Note: Cnt-H for Backspace

**Warning do not use any other power supply than 5V or the board will Fry



---?image=assets/images/gitpitch-audience.jpg
@title[End of Section]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;End of Lab </span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @fa[chevron-right gp-bullet-cyan]  &nbsp;&nbsp;to continue  </span>
 

---?image=assets/images/binary-strings-black2.jpg 
@title[Lab 3 -Build Up Squared Section]
<br><br><br><br><br>
## <p align="center"><span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Build UP Squared</span></p>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>


---?image=/assets/images/slides/Slide12.JPG
@title[Up Squared HW]
### <p align="right"><span class="gold" >EDK II Platform (UP Squared)</span></p>
@snap[south-west span-45 ]
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.56em" >Intel<sup>&reg;</sup> Celeron<sup>tm</sup> processor N3350 Series<br> &lpar;Formerly Apollo Lake&rpar;</span></p>
@snapend


@snap[south-east span-45 ]
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.56em" >
Available from <a href="https://www.aaeon.com/">Aaeon </a> <br> order at: <a href="https://up-shop.org/up-boards/92-up-squared-celeron-duo-core-2gb-memory32gb-emmc.html">here </a>
</span></p>
@snapend

Note:

https://www.google.com/imgres?imgurl=https%3A%2F%2Fksr-ugc.imgix.net%2Fassets%2F014%2F192%2F390%2Fb48b13570b839fdb254d046a4e5fe703_original.png%3Fixlib%3Drb-1.1.0%26crop%3Dfaces%26w%3D1552%26h%3D873%26fit%3Dcrop%26v%3D1479219233%26auto%3Dformat%26frame%3D1%26q%3D92%26s%3Dd8c8e37c0ed5f65b97557dd77e441059&imgrefurl=https%3A%2F%2Fwww.kickstarter.com%2Fprojects%2F802007522%2Fup-squared-the-first-maker-board-with-intel-apollo&docid=hdDbuF0mF4AVzM&tbnid=rQVd58-OYexfgM%3A&vet=10ahUKEwjb-uLy_JDgAhUKsFQKHUnbC7wQMwhCKAIwAg..i&w=1552&h=873&bih=851&biw=1378&q=up%20squared&ved=0ahUKEwjb-uLy_JDgAhUKsFQKHUnbC7wQMwhCKAIwAg&iact=mrc&uact=8


-  Intel® Celerontm processor N3350 Series (Formerly Apollo Lake)



---?image=/assets/images/slides/Slide13.JPG
@title[UP Squared Platform Open Source]
<br>
<p align="left"><span class="gold" ><b>Where to get Open Source<BR> UP Squared</b></span></p>
<br>
- <span style="font-size:0.9em"><font  color="yellow">Open Source </font><a href="https://github.com/tianocore/tianocore.github.io/wiki/IntelAtomProcessorE3900"> UP<sup>2</sup> Wiki</a></span>
  - <span style="font-size:0.9em">V .71 -<a href="https://github.com/tianocore/edk2-platforms/tree/devel-IntelAtomProcessorE3900"> Github Link</a></span>
- <span style="font-size:0.9em"><font  color="white">Binary Object Modules:<br> </font><a href="https://firmware.intel.com/projects/IntelAtomProcessorE3900">firmware.intel.com</a></span>
- <span style="font-size:0.9em">How to Build<a href="https://firmware.intel.com/sites/default/files/intelatome3900-0.71-releasenotes.txt"> Release Notes</a></span>

Note:
- Step by step if NOT downloading Lab release of UP Squared

---?image=/assets/images/slides/Slide14.JPG
@title[UP Squared Platform  Bin Obj]
<br>
<p align="left"><span class="gold" ><b>Where to get Open Source<BR> UP Squared</b></span></p>
<br>
- <span style="font-size:0.9em"><font  color="white">Open Source </font><a href="https://github.com/tianocore/tianocore.github.io/wiki/IntelAtomProcessorE3900"> UP<sup>2</sup> Wiki</a></span>
  - <span style="font-size:0.9em">V .71 -<a href="https://github.com/tianocore/edk2-platforms/tree/devel-IntelAtomProcessorE3900"> Github Link</a></span>
- <span style="font-size:0.9em"><font  color="yellow">Binary Object Modules:<br> </font><a href="https://firmware.intel.com/projects/IntelAtomProcessorE3900">firmware.intel.com</a></span>
- <span style="font-size:0.9em">How to Build<a href="https://firmware.intel.com/sites/default/files/intelatome3900-0.71-releasenotes.txt"> Release Notes</a></span>

Note:
- Step by step if NOT downloading Lab release of UP Squared

---
@title[Download UP Squared Lab Source]
<p align="right"><span class="gold" >@size[1.1](<b>Download UP Squared Lab Source</b>)</span></p>
<p style="line-height:80%" align="left"><span style="font-size:0.9em" >Download the PlatformBuildLab_UP2_FW.zip from : </span><br> @fa[github gp-bullet-white] <span style="font-size:0.7em"><a href="https://github.com/tianocore-training/PlatformBuildLab_UP2_FW/archive/master.zip">github.com PlatformBuildLab_UP2_FW.zip</a></span></p>

<span style="font-size:0.9em" >OR<br>Use `git clone` to download the PlatformBuildLab_UP2_FW<span>
```
$ git clone https://github.com/tianocore-training/PlatformBuildLab_UP2_FW.git
```
<span style="font-size:0.9em" >Directory PlatformBuildLab_UP2_FW will be created</span>
```
   FW 
    - PlatformBuildLab
	   - MV3                    - UP Squared Source for the Labs
	   - BaseToolsUDK.tar.gz    - BaseTools for Linux GCC5 build
	   - FirmwareUpdateX64.efi  - UEFI App to flash Firmware .BIN to Target
	   . . .
```

Note:


---?image=/assets/images/slides/Slide16.JPG
@title[UP Squared Lab Setup]
### <p align="right"><span class="gold" >UP Squared Lab Setup</span></p>
@snap[north-west span-100 ]
<br>
<p style="line-height:70%"><span style="font-size:0.8em"><br>
@color[#87E2A9](Previous Lab Setup Requirements)<br></span>
 <font face="Consolas"><span style="background-color: #000000; font-size:0.550em;"> 
&nbsp; bash$ sudo apt-get install build-essential uuid-dev iasl git gcc-5 nasm  &nbsp;
</span></font><br>
<span style="font-size:0.8em">
@color[#87E2A9](Additional Lab Setup -)</span><br>
<span style="font-size:0.55em">&nbsp;&nbsp;&nbsp;
@color[#87E2A9]( `PlatformLab_FW/FW/PlatformBuildLab`) 
</span></p>

@snapend


@snap[south-west span-100 ]
<p style="line-height:40%" align="left"><span style="font-size:0.55em">
<b>Directories:</b><br>&nbsp;&nbsp;
&bull;MV3<br>&nbsp;&nbsp;
&bull;BuildToolsUDK.tar.gz<br><br>&nbsp;&nbsp;
At the Terminal prompt - install Screen utility for Serial Console to run UEFI Shell<br>&nbsp;&nbsp;
 <font face="Consolas"><span style="background-color: #000000; font-size:0.850em;"> 
&nbsp;&nbsp; bash$ sudo apt-get screen &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></font>
&nbsp;&nbsp;
</snap></p>
<br>
@snapend

@snap[south-east span-70 ]
<p style="line-height:40%" align="left"><span style="font-size:0.55em"><font color="yellow">
<br>&nbsp;&nbsp;
&hyphen;&nbsp;&nbsp;UP Squared  Project source code<br>&nbsp;&nbsp;
&hyphen;&nbsp;&nbsp;Build tools for GCC compiler<br><br>&nbsp;&nbsp;
&nbsp;&nbsp;<br>&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;
</font></snap></p>
<br>
@snapend


Note:
-  Previous Lab Setup Requirements
```
bash$ sudo apt-get install build-essential uuid-dev iasl git gcc-5 nasm 
```
Additional Lab Setup – `       ~src/FW/PlatformBuildLab`

- MV3               	– UP Squared Project source code 
- BuildToolsUDK.tar.gz 	– build tools for GCC compiler 
- At Terminal prompt - Install Screen utility for Serial Console to run UEFI Shell 
```
bash$ sudo apt-get install screen
```	   


---?image=/assets/images/slides/Slide17.JPG
@title[Get the UP Squared Source]
### <p align="right"><span class="gold" >Copy UP Squared Source</span></p>

@snap[north-west span-100 ]
<br>
<p style="line-height:70%"><span style="font-size:0.8em"><br>
Open a terminal prompt(Alt-Cnt-T)<br>
Create a working  space source directory under the home directory<br>
</span>
 <font face="Consolas"><span style="background-color: #000000; font-size:0.60em;"> 
&nbsp;&nbsp; bash$ mkdir ~src &nbsp;&nbsp;&nbsp;&nbsp;
</span></font><br>
<span style="font-size:0.65em">
From the `FW/PlatformBuildLab` folder, copy and paste folder "`~FW/MV3`" to `~src`
</span></p>

@snapend
Note:
- Open a terminal prompt  (Alt-Cnt-T)
- Create a working  space source directory under the home directory
   - bash$ mkdir ~src
- From the FW/PlatformBuildLab folder, copy and paste folder “~FW/MV3” to ~src
 



---?image=/assets/images/slides/Slide18.JPG
@title[Get the BaseTools]
<p align="right"><span class="gold" ><b>Get the `BaseTools` for UP Squared </b> </span></p>
@snap[north-west span-100 ]
<br>
<br>
<p style="line-height:70%"><span style="font-size:0.8em">
Rename or <b>mv</b> the directory @size[.8em]("`~src/MV3/edk2/BaseTools`")<br>
</span>
 <font face="Consolas"><span style="background-color: #000000; font-size:0.650em;"> 
&nbsp;&nbsp; bash$ cd ~src/MV3/edk2 &nbsp;&nbsp;&nbsp;&nbsp;<br>
&nbsp;&nbsp; bash$ mv BaseTools BaseToolsX &nbsp;&nbsp;<br>
&nbsp;&nbsp; bash$ tar -xf BaseToolsUDK.tar.xz &nbsp;&nbsp;<br>
</span></font><br>
<span style="font-size:0.7em">
Extract the file @size[.8em](`~FW/PlatformBuildLab/BaseToolsUDK.tar.gz`)  to  @size[.8em](`~src/MV3/edk2`)
</span></p>

@snapend

Note:

-  Extract the Rename or mv the directory “~src/MV3/edk2/BaseTools”
```
 bash$ cd ~src/MV3/edk2<Br>
 bash$ mv BaseTools BaseTools
```

- Extract the file ~FW/PlatformBuildLab/BaseToolsMax.tar.gz  to  ~src/MV3/edk2
  - bash$ tar -xf BaseToolsUDK.tar.xz 
  


---
@title[Platform Source Directory Structure]
### <p align="right"><span class="gold" >Platform Source Directory Structure </span></p>

```bash
 ~src/MV3 (Work Space Dir)

	/edk2
		/(UDK2018 Directories)
		/BaseTools (from BaseToolsUDK.tar.gz)

	/edk2-platforms  

		/Platform

			/BroxtonPlatformPkg 
				(Platform Dirs)
				PlatformPkg.dec
				PlatformPkg.fdf
				PlatformPkgnn.dsc
		/Silicon

			/BroxtonSoC
				/BroxtonFspPkg
				/BroxtonSiPkg

```

@snap[north-east span-75 fragment]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:40%" align="left"><span style="font-size:0.7em"><br><br>&nbsp;</span></p>
<p style="line-height:50%" align="left"><span style="font-size:0.7em">
<font color="yellow">@size[1.1em](&larr;<b>&mdash;&mdash;&mdash;&mdash;&mdash;&mdash;</b>)Invoke the build script from here</font><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@size[.7em](@color[#87E2A9](`BuildBIOS`) script)
</span></p>
@snapend


@snap[north-east span-65 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" align="left"><span style="font-size:0.7em"><br><br><br><br>
<font color="yellow">@size[1.1em](&larr;<b>&mdash;&mdash;</b>)Project platform directory </font><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@size[.7em](&lpar;includes platform build scripts)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@size[.7em](@color[#87E2A9](`BuildIFWI`) that then calls &nbsp; &rarr;&nbsp; @color[#87E2A9](`BuildBxtBios`))<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@size[.7em](  - Called from @color[#87E2A9](`BuildBIOS`) above &rpar;)
</span></p>
@snapend


Note:
-  Platform Source Directory Structure
   -  Build from /edk2-platform  directory
   -  Project platform directory is: BroxtonPlatformPkg




---
@title[Steps to Build & Install Firmware]
<br>
### <p align="center"><span class="gold" >Steps to Build & Install Firmware</span></p>
<ul style="list-style-type:none; line-height:0.9;">
  <li><span style="font-size:0.9em">@size[1.125em](<font color="yellow"> &#10102;</font>)&nbsp; Open Terminal prompt & Cd to <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@size[.7em]( `$HOME/src/Max/edk2-platforms/Vlv2TbltDevicePkg`)</span></li>
  <li><span style="font-size:0.9em">@size[1.125em](<font color="yellow"> &#10103;</font>)&nbsp; Fix-up "chmod" bin executable files</span></li>
  <li><span style="font-size:0.9em">@size[1.125em](<font color="yellow"> &#10104;</font>)&nbsp; Invoke the build process script, `BuildBIOS`</span></li>
  <li><span style="font-size:0.9em">@size[1.125em](<font color="yellow"> &#10105;</font>)&nbsp; Locate build output (.BIN file for BIOS image)</span></li>
  <li><span style="font-size:0.9em">@size[1.125em](<font color="yellow"> &#10106;</font>)&nbsp; Flash binary image onto the platform</span></li>
  <li><span style="font-size:0.9em">@size[1.125em](<font color="yellow"> &#10107;</font>)&nbsp; Reset and verify new firmware</span></li>
</ul>
<br>
<br>
<span style="font-size:0.9em"><font color="yellow"><i><b>Next slides will follow the above steps</b></i></font></span>


Note:

Slide says it all
---
@title[fix-up shell properties ]
<br>
<p align="left"><span class="gold" >@size[1.1](<b>Fix-up Script Properties to Execute</b>)</span></p>
<p style="line-height:70%"><span style="font-size:0.8em">
@size[1.25em](<font color="yellow"> &#10102;</font>)&nbsp;&nbsp;Open Terminal prompt (Cnt-Alt-T) & <br>
&nbsp; &nbsp; &nbsp; &nbsp; Cd to work space directory<br>
@size[1.25em](<font color="yellow"> &#10103;</font>)&nbsp;&nbsp;Fix Binary tools to "execute"  with `chmod +x`
</span></p>
<BR>

```
 
 bash$ cd ~src/src/MV3/edk2-platforms/BroxtonPlatformPkg/Common/Tools

 
 bash$ chmod +x GenBiosID/GenBIosId
 
 bash$ chmod +x FCE/FCE

 bash$ chmod +x FCE/BfmLib

```

Note:
 Slide says it all


---
@title[Platform Build Scripts]
<p align="right"><span class="gold" >@size[1.1em](<b>Platform Build Scripts</b>)</span></p>

@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%" align="center"><span style="font-size:0.8em">Platform Build Scripts<br>&nbsp; </span></p>)
<p style="line-height:80%"><span style="font-size:0.8em">Many Platforms have a bash or bat script file to pre or post process the EDK II build process</span></p>

<p style="line-height:70%"><span style="font-size:0.7em">For UP Squared Broxton Platform : @color[#87E2A9](`BuildBIOS.bat`) or @color[#87E2A9](`BuildBIOS.sh`) calls: <br></span>
<span style="font-size:0.7em"><br>
&nbsp;&nbsp;@color[#87E2A9](`BuildIFWI`) from the platform package directory <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`.. Platform/BroxtonPlatformPkg` <br>
&nbsp;&nbsp;&nbsp;&ndash; pre build processing <br>
&nbsp;&nbsp;&nbsp;&ndash;  calls @color[#87E2A9](`BuildBxtBios`) - a platform script to preform the EDK II `build` <br> 
&nbsp;&nbsp;&nbsp;&ndash; determines date <br>
&nbsp;&nbsp;&nbsp;&ndash; board ID<br>
&nbsp;&nbsp;&nbsp;&ndash; post build stitching<br>
</span></p>

Note:

For the platform edk II builds usually a script is called that will do pre and post build processing.  

There is also this capability that is part of the .dsc but many developers have not taken advantage of this feature


---?image=/assets/images/slides/Slide23.JPG
@title[Build Process for DEBUG]
### <p align="right"><span class="gold" >Build Process for DEBUG BIOS </span></p>

@snap[north-west span-20  ]
<br>
<br>
<br>
<br>
@size[1.125em](<font color="yellow"> &#10104;</font>)
@snapend

@snap[north-east span-95  ]
<br>
<br>
<p align="left"><span style="font-size:0.85em">From Terminal Prompt enter:  &nbsp;&nbsp;</span><span style="font-size:0.6em"><font color="yellow">Note: <i> the Build will Pause</i></font></span></p>
<pre>
```
bash$ cd ~/src/MV3/edk2-platforms
bash$ . BuildBIOS.sh /UP /A Broxton Debug

```
</pre>
@snapend



Note:

Press Enter to continue.
Also notice the BUILD DEFINE Statements from the file:  DefineAtBuildMacros.dsc



---
@title[Examine Command Line & Build Parameters]
<p align="right"><span class="gold" >@size[1.1em](<b>Examine Build Parameters</b>)</span></p>

@snap[north-west span-100 ]
<br>
<br>
@box[bg-black text-yellow rounded my-box-pad2  ](<p style="line-height:60%" align="left"><span style="font-size:0.65em; font-family:Consolas; " >&nbsp;&nbsp;build<br><br><br>&nbsp;&nbsp;</span></p>)
@snapend


@snap[north-east span-85  fragment]
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.60em; font-family:Consolas; " >
<font color="#75deFF">&nbsp;&nbsp;  -D LOGGING=TRUE&nbsp;&nbsp; -D UP2_BOARD=TRUE<br>
 . . . -D <i> Option &lpar;n&rpar;</i> </font>
</span></p>
@snapend


@snap[north-east span-30  fragment]
<br>
<br>
<p style="line-height:40%" align="left"><span style="font-size:0.8em"><br></span></p>
@box[bg-white text-black rounded my-box-pad2  ](<p style="line-height:70%" align="left"><span style="font-size:0.8em"><font color="blue"><b>&nbsp;&nbsp;MACROS</font><br>&nbsp;&nbsp;Logging<br>&nbsp;&nbsp;UP<sup>2</sup> Board<br>&nbsp;&nbsp;</b></span></p>)
@snapend


@snap[north-west span-100 fragment ]
<br>
<br>
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.8em"><font color="#87E2A9"><br><br><b>Properties from `Conf\Target.txt`</b></font></span></p>
<table id="recTable">
	<tr class="fragment">
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>TARGET</b></span></p></td>
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>= @color[yellow](DEBUG)</b></span></p></td>
		<td align="left" bgcolor="#0070C0" height=".0025"><p style="line-height:010%"><span style="font-size:0.6em" ><b>Build Mode</b></span></p></td>
	</tr>
	<tr class="fragment">
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>TARGET_ARCH</b></span></p></td>
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>= @color[yellow](IA32 X64)</b></span></p></td>
		<td align="left" bgcolor="#0070C0" height=".0025"><p style="line-height:010%"><span style="font-size:0.6em" ><b>CPU Architecture</b></span></p></td>
	</tr>
	<tr class="fragment">
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>TOOL_CHAIN_TAG</b></span></p></td>
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>= @color[yellow](VS2015x86)</b></span></p></td>
		<td align="left" bgcolor="#0070C0" height=".0025"><p style="line-height:010%"><span style="font-size:0.6em" ><b>VS Tool Chain</b></span></p></td>
	</tr>
	<tr class="fragment">
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>ACTIVE_PLATFORM</b></span></p></td>
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:040%"><span style="font-size:0.460em; font-family:Consolas; " ><b>= @color[yellow](BroxtonPlatformPkg /PlatformPkgX64)</b></span></p></td>
		<td align="left" bgcolor="#0070C0" height=".0025"><p style="line-height:010%"><span style="font-size:0.6em" ><b>Platform DSC file</b></span></p></td>
	</tr>
	<tr class="fragment">
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:040%"><span style="font-size:0.460em; font-family:Consolas; " ><b>MAX&lowbar;CONCURRENT&lowbar; THREAD_NUMBER</b></span></p></td>
		<td align="left" bgcolor="#404040" height=".0025"><p style="line-height:010%"><span style="font-size:0.460em; font-family:Consolas; " ><b>= @color[yellow](1)</b></span></p></td>
		<td align="left" bgcolor="#0070C0" height=".0025" width="35%"><p style="line-height:010%"><span style="font-size:0.6em" ><b>Thread Count</b></span></p></td>
	</tr>
</table>


@snapend

---
@title[Examine Platform Parameters UP Squared Specific]
<p align="right"><span class="gold" >@size[1.1em](<b>Platform Build and PCD Parameters</b>)</span></p>

@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%" align="center"><span style="font-size:0.8em">Platform Parameters<br>&nbsp; </span></p>)
<p style="line-height:80%"><span style="font-size:0.8em">Many Platform Parameters are defined in  a top .DSC file that controls  PCD and build switches</span></p>

<p style="line-height:70%"><span style="font-size:0.7em">For UP Squared : </span></p>
  <ul style="list-style-type:none; line-height:0.7;">
    <li><span style="font-size:0.7em">@color[yellow]( Build Switches )&lpar;<i>dynamic</i>&rpar; </span></li>
	<ul style="list-style-type:none; line-height:0.7;">
		<li><span style="font-size:0.6em">`DefineAtBuildMacros.dsc ` - Updated from `BuildBIOS` command line</span></li>
		<li><span style="font-size:0.6em"> `PlatformDsc/BuildOptionsEDKII.dsc ` - Like PCDs on command line</span></li>
	</ul>	
    <li><span style="font-size:0.7em">@color[yellow](EDK II feature Options)  </span></li>
 	<ul style="list-style-type:none; line-height:0.7;">
		<li><span style="font-size:0.6em">`PlatformDsc/Defines.dsc ` - Manually update before build command line</span></li>
	</ul>	

  </ul>


Note:

many will have "ifdef" statements in the major .dsc file in order to enable a feature or not


---?image=/assets/images/slides/Slide26.JPG
@title[Build Process for Release]
### <p align="right"><span class="gold" >Build Process for Release</span></p>
@snap[north-west span-20  ]
<br>
<br>
<br>
@size[1.125em](<font color="yellow"> &#10104;</font>)
@snapend

@snap[north-east span-95  ]
<br>
<br>
<p align="left"><span style="font-size:0.85em">From Terminal Prompt enter:  &nbsp;&nbsp;</span></p>
<pre>
```
bash$ . BuildBIOS.sh /UP /A Broxton Release
```
</pre>
@snapend




@snap[north-east span-30  fragment]
<br>
<br>
<br>
<br>
<p style="line-height:40%" align="left"><span style="font-size:0.8em"><br></span></p>
@box[bg-white text-black rounded my-box-pad2  ](<p style="line-height:70%" align="left"><span style="font-size:0.8em"><font color="blue"><b>&nbsp;&nbsp;Note MACRO</font><br>&nbsp;&nbsp;Logging<br>&nbsp;&nbsp;<font color="blue">Set to FALSE</font><br>&nbsp;&nbsp;</b></span></p>)
@snapend



Note:
From  Terminal Prompt enter:
```
$ cd edk2-Platforms
$ BuildBIOS.sh /UP /A Broxton Release

```

---
@title[DEBUG & RELEASE Differences]
### <p align="right"><span class="gold" >DEBUG & RELEASE Differences</span></p>

@box[bg-purple-pp text-white rounded my-box-pad2 fragment](<p style="line-height:70%"><span style="font-size:0.9em" >Slower boot because the time it takes to display debug info <br>&nbsp; </span></p>)
@box[bg-green-pp text-white rounded my-box-pad2 fragment](<p style="line-height:70%"><span style="font-size:0.9em" >Larger image because of debug code & embedded info<br>&nbsp;  </span></p>)
@box[bg-gold2 text-white rounded my-box-pad2  fragment](<p style="line-height:70%"><span style="font-size:0.9em" >Uses the serial port for debug string output<br>&nbsp; </span></p>)
@box[bg-royal text-white rounded my-box-pad2  fragment](<p style="line-height:80%"><span style="font-size:0.9em" >Contains detailed debug strings that show the<br> boot progress and various `ASSERT` / `TRACE` errors<br>&nbsp; </span></p>)

 
Note:

### DEBUG build …
- Contains detailed debug strings that show the boot process, along with various ASSERT/TRACE errors
- Uses the serial port for debug string output
- Larger image than RELEASE, due to the embedded debug info
- Slower boot than RELEASE, due to the time it takes to display the debug info


### RELEASE build …
- Does not contain the debug strings
- Does not use the serial port for debug output
- Smaller image than DEBUG
- Faster boot than DEBUG

---?image=/assets/images/slides/Slide28.JPG
@title[Build Process Completed]
### <p align="right"><span class="gold" >Build Process Completed</span></p>
<span style="font-size:0.9em" >@size[1.25em](<font color="yellow"> &#10105;</font>)&nbsp;&nbsp;Locate the build .BIN image</span>

@snap[south-west span-100  ]
<p style="line-height:80%" align="left"><span style="font-size:0.9em" >
The platform build script post build process will stitch the multiple firmware volumes generated by the EDK II build process into the final <b> .BIN</b> image.<br><br>
The script displays the location of the final <b>.BIN </b> file<br><br>
</span></p>
@snapend

Note:
- The EDK II build generates multiple firmware volumes, which are combined in the .BIN image
- typically the platform script will call a stitching process to combine all the images together in  post processing after the EDK II build

---
@title[Flash onto the UP Squared]
### <p align="right"><span class="gold" >Flashing the New BIOS</span></p>
@snap[north-west span-100  ]
<br>
<br>
<span style="font-size:0.9em" >@size[1.25em](<font color="yellow"> &#10106;</font>)&nbsp;&nbsp;Flash the binary image</span>
@snapend


<br>
1.  <span style="font-size:0.85em" >&nbsp;&nbsp;Access UP Squared Binary image file from build folder</span>
  - <span style="font-size:0.5em" >`~src/MV3/edk2-platforms\Platform\BroxtonPlatformPkg\Common\Tools\Stitch`</span>
  - <span style="font-size:0.65em" >DEBUG 	UPBOARDA.X64.D01.0071._GCC.bin</span>
  - <span style="font-size:0.65em" >RELEASE	UPBOARDA.X64.R01.0071._GCC.bin</span>
2. <span style="font-size:0.85em" >&nbsp;&nbsp;Copy BIN files to a USB Thumb drive</span>
3. <span style="font-size:0.85em" >&nbsp;&nbsp;Copy </span><span style="font-size:0.65em" >`FirmwareUpdateX64.efi`</span><span style="font-size:0.85em" > to a USB thumb &nbsp;&nbsp;drive from @size[.65em](`.../FW/PlatformBuildLab`)</span>
4. <span style="font-size:0.85em" >&nbsp;&nbsp;Reset the UP Squared board and be prepared to type "F2" to enter System Setup</span>

Note:
1.  Access UP2 Binary image file from build folder
  - C:\FW\MV3\edk2-platforms\Platform\BroxtonPlatformPkg\Common\Tools\Stitch
  - DEBUG 	   UPBOARDA.X64.0071.D01._date_.bin
  - RELEASE	UPBOARDA.X64.0071.R01._date_.bin

2. Copy BIN files to a USB Thumb drive
3. Copy FirmwareUpdateX64.efi to a USB thumb drive from $.../FW/PlatformBuildLab
4. Reset the UP Squared board and be prepared to type “F2” to enter System Setup 

---?image=/assets/images/slides/Slide30.JPG
@title[Flash onto the UP Squared 02]
### <p align="right"><span class="gold" >Flashing the New BIOS</span></p>
<span style="font-size:0.75em" >5. &nbsp;&nbsp;Set "`BIOS Lock`" to "`Disable`" in the Setup by the following:</span>
<ul style="list-style-type:disc; line-height:0.6;">
  <li> <span style="font-size:0.6em" >Inside Setup go to "`Device Manager`"  &rarr;   "`System Setup`" &rarr; "`South Cluster Configuration`" &rarr;  "`Miscellaneous Configuration`"  </span></li>
  <li> <span style="font-size:0.6em" >Open "`BIOS Lock`" and select "`Disable`"  </span></li>
  <li> <span style="font-size:0.6em" >Press "`F10`"  to save and then reboot</span></li>
</ul>


Note:

the platform setup is reached by typing F2 on a reboot


---?image=/assets/images/slides/Slide31.JPG
@title[Flash onto the UP Squared  03]
### <p align="right"><span class="gold" >Flashing the New BIOS</span></p>

<p style="line-height:80%"><span style="font-size:0.85em" >6.&nbsp;&nbsp;Boot into the UEFI Shell  then  type "FS0:"&nbsp;<br>7.&nbsp;&nbsp;Run update `.efi` utility with either BIN file </span> <span style="font-size:0.6em" >&lpar;<i>Note</i> the “TAB” Key <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;will fill out the command line for you &rpar;</span></p>

```
  FS0:\> FirmwareUpdateX64.efi UPBORA.X64_R_0071_01_GCC.bin
 
```
<span style="font-size:0.75em" >Wait for the new firmware update to finish</span>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:70%"><span style="font-size:0.85em" >&nbsp;&nbsp;Reset and boot new firmware</span></p>

 
Note:

6, Boot into the UEFI Shell  then  type “FS0:”
7, Run update .efi utility with either BIN file  
	(Note the “TAB” Key will fill out the command line for you )
```
FS0:\> FirmwareUpdateX64.efi UPBORA.X64_R_0071_01_GCC.bin
 
```
Reset and boot new firmware


---?image=/assets/images/slides/Slide32.JPG
@title[Verify after Firmware Update]
### <p align="right"><span class="gold" >Verify after Firmware Update</span></p>
@snap[north-west span-100  ]
<br>
<br>
<span style="font-size:0.9em" >@size[1.25em](<font color="yellow"> &#10107;</font>)&nbsp;&nbsp;Reboot and Verify</span>
@snapend

<br>
- <span style="font-size:0.85em" >Verify that the Firmware was updated by checking the Date</span>
- <span style="font-size:0.85em" >Go into setup by pressing "F2" after reboot</span>
- <span style="font-size:0.85em" >The EDK II front page will show the BIOS ID with Date/time stamp</span>


Note:
- Verify that the Firmware was updated by checking the Date
- Go into setup by pressing “F2” after reboot
- The EDK II front page will show the BIOS ID with Date/time stamp



---  
@title[Summary]
##### <p align="center"<span class="gold"   >Summary </span></p><br>

 @fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Hardware Setup for UP Squared  </span><br><br>
 @fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Build a EDK II Platform using UP Squared  </span> <br><br>
 

---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/questions.JPG =10x) 


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)


---
@title[Acknowledgements]
#### <p align="center"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2019, Intel Corporation. All rights reserved.
**/

```


---?image=assets/images/binary-strings-black2.jpg
@title[Backup Section]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Back up</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>

---  
@title[Build Errors]
<br>
<br>
<br>
<br>
##### <p align="center"<span class="gold"   >Build Errors</span></p><br>


---
@title[Build Error- RC.exe ]
<p align="right"><span class="gold" ><b>Build Error- RC.exe </b></span></p>
<p style="line-height:90%"><span style="font-size:0.9em" >Because RC.Exe is not found, Error Message:</span></p>

```
   "c:\Program Files (x86)\Windows Kits\8.0\bin\x64\rc.exe" 
/Foc:\edkii.svn\Build\NT32IA32\DEBUG_VS2013x86\IA32\MdeModulePkg\Application\HelloWorld\HelloWorld\OUTPUT
\HelloWorldhii.lib 
c:\edkii.svn\Build\NT32IA32\DEBUG_VS2013x86\IA32\MdeModulePkg\Application\HelloWorld\HelloWorld\OUTPUT\He
lloWorldhii.rc
'c:\Program' is not recognized as an internal or external command,
operable program or batch file.
 
NMAKE : fatal error U1077: '"c:\Program Files (x86)\Windows Kits\8.0\bin\x64\rc.exe' : return code '0x1'
Stop.

```

<p style="line-height:90%"><span style="font-size:0.9em" >Find where the RC.EXE is located on your VS Installation:  </span></p>

<p style="line-height:90%"><span style="font-size:0.9em" >Example (VS 2013):  The RC.exe is located on this machine: <br>
<span style="font-size:0.5em" >`C:\Program Files (x86)\Windows Kits\8.1\bin\x64` </span></span></p>
<span style="font-size:0.9em" >Edit `Conf/tools_def.txt` </span>

Note:


+++
@title[Build Error- RC.exe 02]
<p align="right"><span class="gold" ><b>Build Error- RC.exe Cont...</b></span></p>

<span style="font-size:0.9em" >Edit `Conf/tools_def.txt` </span><br>
<p style="line-height:90%"><span style="font-size:0.9em" >Search for your installation of Visual Studio (2013 or 2015)</span></p>
<p style="line-height:90%"><span style="font-size:0.9em" >Update according to the path for where the RC.EXE is found </span></p>

```
# Microsoft Visual Studio 2013 Professional Edition
DEFINE WINSDK8_BIN       = c:\Program Files\Windows Kits\8.1\bin\x86\
DEFINE WINSDK8x86_BIN    = c:\Program Files (x86)\Windows Kits\8.1\bin\x64
 
# Microsoft Visual Studio 2015 Professional Edition
DEFINE WINSDK81_BIN       = c:\Program Files\Windows Kits\8.1\bin\x86\
DEFINE WINSDK81x86_BIN    = c:\Program Files (x86)\Windows Kits\8.1\bin\x64

```


Note:



---?image=/assets/images/slides/Slide40.JPG
@title[Visual Studio Resource Compiler Error – Rc.exe]
<p align="right"><span class="gold" >Visual Studio Resource Compiler Error – Rc.exe</span></p>
 
Note:
- The Rc.exe was not found and the build fails
- Find where rc.exe is located and update the  tools_def.txt

- Update `MV3/conf/tools_def.txt`
<pre>
- # Microsoft Visual Studio 2013 Professional Edition
- DEFINE WINSDK8x86_BIN    = C:\Program Files (x86)\Windows Kits\8.1\bin\x64

- # Microsoft Visual Studio 2015 Professional Edition
- DEFINE WINSDK81x86_BIN   = C:\Program Files (x86)\Windows Kits\8.1\bin\x64

- # Microsoft Visual Studio 2017 Professional Edition
- DEFINE WINSDK10_BIN      =  Location of Rc.exe
</pre>


