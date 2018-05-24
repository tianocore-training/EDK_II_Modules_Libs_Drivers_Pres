---?image=assets/images/gitpitch-audience.jpg
@title[EDK II Modules]
<br><br><br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### EDK II Modules: Libs, Drivers & Apps

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  EDK II Modules: Libs, Drivers & Apps Pres

  Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

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
<BR>
### <p align="center"<span class="gold"   >Lesson Objective </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
<br>
 @fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;What is a EDK II Module</span><br>
 @fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Use EDK II libraries to write UEFI apps/drivers</span><br>
 @fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;How to Define a UEFI application</span> <br>
 @fa[certificate gp-bullet-magenta]<span style="font-size:0.9em">&nbsp;&nbsp;Differences between UEFI App / Drivers INF file</span><br>


---?image=assets/images/binary-strings-black2.jpg
@title[Modules Overview Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EDK II Modules Overview</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;What are EDK II Modules</span>


 
---?image=/assets/images/slides/Slide4.JPG
<!-- .slide: data-transition="none" -->
@title[Modules]
### <p align="right"><span class="gold" >Modules</span></p>

Note:

So the first thing we have in trying to break EDK II down is Modules:
 
- A module is the smallest separate object compiled in the EDK II.  A module is a single resultant .EFI file.
- Module examples:
- A UEFI/DXE driver 
- A PEIM
- A UEFI application
- A Library 

- All of these could be a module.  A modules could  be one entity



+++?image=/assets/images/slides/Slide5.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Modules 02]
### <p align="right"><span class="gold" >Modules</span></p>
<br>
Smallest separate object compiled in EDK II

Note:

So the first thing we have in trying to break EDK II down is Modules:
 
- A module is the smallest separate object compiled in the EDK II.  A module is a single resultant .EFI file.
- Module examples:
- A UEFI/DXE driver 
- A PEIM
- A UEFI application
- A Library 

- All of these could be a module.  A modules could  be one entity



 
---?image=/assets/images/slides/Slide7.JPG
@title[Module Types]
### <p align="right"><span class="gold" >Module Types</span></p>

Note:

- BASE 
- SEC  
- PEI_CORE 
- PEIM  
- DXE_CORE 
- DXE_DRIVER 
- DXE_RUNTIME_DRIVER 
- DXE_SAL_DRIVER 
- DXE_SMM_DRIVER 
- UEFI_DRIVER 
- UEFI_APPLICATION
- BASE LIBRARY
- SECURITY_CORE 
- PEI_CORE 
- COMBINED_PEIM_DRIVER 
- PIC_PEIM
- RELOCATABLE_PEIM 
- BS_DRIVER 
- RT_DRIVER 
- SAL_RT_DRIVER 
- APPLICATION


---?image=/assets/images/slides/Slide9.JPG
<!-- .slide: data-transition="none" -->
@title[Module Source - minimum files]
<p align="right"><span class="gold" >Module Source Contents </span><span style="font-size:0.8em" >- minimum files</span></p>

Note:

+++?image=/assets/images/slides/Slide10.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Module Source - minimum files 02 ]
<p align="right"><span class="gold" >Module Source Contents </span><span style="font-size:0.8em" >- minimum files</span></p>

Note:

+++?image=/assets/images/slides/Slide11.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Module Source - minimum files 03 ]
<p align="right"><span class="gold" >Module Source Contents </span><span style="font-size:0.8em" >- minimum files</span></p>

Note:

+++?image=/assets/images/slides/Slide12.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Module Source - minimum files 04 ]
<p align="right"><span class="gold" >Module Source Contents </span><span style="font-size:0.8em" >- minimum files</span></p>

Note:

+++?image=/assets/images/slides/Slide13.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Module Source - minimum files 05 ]
<p align="right"><span class="gold" >Module Source Contents </span><span style="font-size:0.8em" >- minimum files</span></p>

Note:



---?image=assets/images/binary-strings-black2.jpg
@title[EDK II Library Modules Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EDK II Library Modules</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>


---?image=/assets/images/slides/Slide16.JPG
<!-- .slide: data-transition="none" -->
@title[Library Class ]
<p align="right"><span class="gold" >Library Class</span></p>

Note:

#### Syntax

- [LibraryClasses.common]
-   <LibraryClassName>|<LibraryInstancePathToInf/Name.inf>
-   DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

It has a library class name, a pipe symbol and then a library instance, which is identified by the path to the INF, then the INF itself. 

So for example, the “DebugLib”, class is identified by the MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
The library instance, BaseDebugLibNull, has all the required interfaces for debug Lib.  And that’s the one that will be linked against the modules in this example.


- Consistent set of interfaces 
#### First, a basic library class definition: <br>
A library class is a set of interfaces; it does not have any implementation information

It is identified by one GUID. And usually contains
- some macros, 
- sometimes global variables, 
- some functions uniquely

 Each library class has one GUID, and there is a mapping of a library class to library instance. 
For example there may be three library instances for a given function and one library class that they would all represent. In this example, the DSC file is going to map library class to a library instance.


- Does not describe implementation of the interfaces
- The implementation is decided at the platform level
- DSC file maps class to instance

- library class

- At the top of the slide there is an example of [libraryclasses.common] for a DSC file.



+++?image=/assets/images/slides/Slide17.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Class 02]
<p align="right"><span class="gold" >Library Class</span></p>

Note:

#### Syntax

- [LibraryClasses.common]
-   <LibraryClassName>|<LibraryInstancePathToInf/Name.inf>
-   DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

It has a library class name, a pipe symbol and then a library instance, which is identified by the path to the INF, then the INF itself. 

So for example, the “DebugLib”, class is identified by the MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
The library instance, BaseDebugLibNull, has all the required interfaces for debug Lib.  And that’s the one that will be linked against the modules in this example.


- Consistent set of interfaces 
#### First, a basic library class definition: <br>
A library class is a set of interfaces; it does not have any implementation information

It is identified by one GUID. And usually contains
- some macros, 
- sometimes global variables, 
- some functions uniquely

 Each library class has one GUID, and there is a mapping of a library class to library instance. 
For example there may be three library instances for a given function and one library class that they would all represent. In this example, the DSC file is going to map library class to a library instance.


- Does not describe implementation of the interfaces
- The implementation is decided at the platform level
- DSC file maps class to instance

- library class

- At the top of the slide there is an example of [libraryclasses.common] for a DSC file.



+++?image=/assets/images/slides/Slide18.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Class 03]
<p align="right"><span class="gold" >Library Class</span></p>

Note:

#### Syntax

- [LibraryClasses.common]
-   <LibraryClassName>|<LibraryInstancePathToInf/Name.inf>
-   DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

It has a library class name, a pipe symbol and then a library instance, which is identified by the path to the INF, then the INF itself. 

So for example, the “DebugLib”, class is identified by the MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
The library instance, BaseDebugLibNull, has all the required interfaces for debug Lib.  And that’s the one that will be linked against the modules in this example.


- Consistent set of interfaces 
#### First, a basic library class definition: <br>
A library class is a set of interfaces; it does not have any implementation information

It is identified by one GUID. And usually contains
- some macros, 
- sometimes global variables, 
- some functions uniquely

 Each library class has one GUID, and there is a mapping of a library class to library instance. 
For example there may be three library instances for a given function and one library class that they would all represent. In this example, the DSC file is going to map library class to a library instance.


- Does not describe implementation of the interfaces
- The implementation is decided at the platform level
- DSC file maps class to instance

- library class

- At the top of the slide there is an example of [libraryclasses.common] for a DSC file.


+++?image=/assets/images/slides/Slide19.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Class 04]
<p align="right"><span class="gold" >Library Class</span></p>

Note:

#### Syntax

- [LibraryClasses.common]
-   <LibraryClassName>|<LibraryInstancePathToInf/Name.inf>
-   DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

It has a library class name, a pipe symbol and then a library instance, which is identified by the path to the INF, then the INF itself. 

So for example, the “DebugLib”, class is identified by the MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
The library instance, BaseDebugLibNull, has all the required interfaces for debug Lib.  And that’s the one that will be linked against the modules in this example.


- Consistent set of interfaces 
#### First, a basic library class definition: <br>
A library class is a set of interfaces; it does not have any implementation information

It is identified by one GUID. And usually contains
- some macros, 
- sometimes global variables, 
- some functions uniquely

 Each library class has one GUID, and there is a mapping of a library class to library instance. 
For example there may be three library instances for a given function and one library class that they would all represent. In this example, the DSC file is going to map library class to a library instance.


- Does not describe implementation of the interfaces
- The implementation is decided at the platform level
- DSC file maps class to instance

- library class

- At the top of the slide there is an example of [libraryclasses.common] for a DSC file.


+++?image=/assets/images/slides/Slide20.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Class 05]
<p align="right"><span class="gold" >Library Class</span></p>

Note:

#### Syntax

- [LibraryClasses.common]
-   <LibraryClassName>|<LibraryInstancePathToInf/Name.inf>
-   DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

It has a library class name, a pipe symbol and then a library instance, which is identified by the path to the INF, then the INF itself. 

So for example, the “DebugLib”, class is identified by the MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
The library instance, BaseDebugLibNull, has all the required interfaces for debug Lib.  And that’s the one that will be linked against the modules in this example.


- Consistent set of interfaces 
#### First, a basic library class definition: <br>
A library class is a set of interfaces; it does not have any implementation information

It is identified by one GUID. And usually contains
- some macros, 
- sometimes global variables, 
- some functions uniquely

 Each library class has one GUID, and there is a mapping of a library class to library instance. 
For example there may be three library instances for a given function and one library class that they would all represent. In this example, the DSC file is going to map library class to a library instance.


- Does not describe implementation of the interfaces
- The implementation is decided at the platform level
- DSC file maps class to instance

- library class

- At the top of the slide there is an example of [libraryclasses.common] for a DSC file.


+++?image=/assets/images/slides/Slide21.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Class 06]
<p align="right"><span class="gold" >Library Class</span></p>

Note:

#### Syntax

- [LibraryClasses.common]
-   <LibraryClassName>|<LibraryInstancePathToInf/Name.inf>
-   DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

It has a library class name, a pipe symbol and then a library instance, which is identified by the path to the INF, then the INF itself. 

So for example, the “DebugLib”, class is identified by the MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf
The library instance, BaseDebugLibNull, has all the required interfaces for debug Lib.  And that’s the one that will be linked against the modules in this example.


- Consistent set of interfaces 
#### First, a basic library class definition: <br>
A library class is a set of interfaces; it does not have any implementation information

It is identified by one GUID. And usually contains
- some macros, 
- sometimes global variables, 
- some functions uniquely

 Each library class has one GUID, and there is a mapping of a library class to library instance. 
For example there may be three library instances for a given function and one library class that they would all represent. In this example, the DSC file is going to map library class to a library instance.


- Does not describe implementation of the interfaces
- The implementation is decided at the platform level
- DSC file maps class to instance

- library class

- At the top of the slide there is an example of [libraryclasses.common] for a DSC file.



---?image=/assets/images/slides/Slide23.JPG
<!-- .slide: data-transition="none" -->
@title[NULL Library Class]
<p align="right"><span class="gold" >"NULL" Library Class</span></p>

Note:
- Not a named library
- Not related to LibNull instances (DebugLibNull)
- May not produce any interfaces
- Does all work in constructors
- Can be linked more than once
- Used for special cases
- DXE Core and DXE IPL section file interpreters

+++?image=/assets/images/slides/Slide24.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[NULL Library Class 02]
<p align="right"><span class="gold" >"NULL" Library Class</span></p>

Note:
- Not a named library
- Not related to LibNull instances (DebugLibNull)
- May not produce any interfaces
- Does all work in constructors
- Can be linked more than once
- Used for special cases
- DXE Core and DXE IPL section file interpreters


+++?image=/assets/images/slides/Slide25.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[NULL Library Class 03]
<p align="right"><span class="gold" >"NULL" Library Class</span></p>

Note:
- Not a named library
- Not related to LibNull instances (DebugLibNull)
- May not produce any interfaces
- Does all work in constructors
- Can be linked more than once
- Used for special cases
- DXE Core and DXE IPL section file interpreters


+++?image=/assets/images/slides/Slide26.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[NULL Library Class 04]
<p align="right"><span class="gold" >"NULL" Library Class</span></p>

Note:
- Not a named library
- Not related to LibNull instances (DebugLibNull)
- May not produce any interfaces
- Does all work in constructors
- Can be linked more than once
- Used for special cases
- DXE Core and DXE IPL section file interpreters


+++?image=/assets/images/slides/Slide27.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[NULL Library Class 05]
<p align="right"><span class="gold" >"NULL" Library Class</span></p>

Note:
- Not a named library
- Not related to LibNull instances (DebugLibNull)
- May not produce any interfaces
- Does all work in constructors
- Can be linked more than once
- Used for special cases
- DXE Core and DXE IPL section file interpreters

---?image=/assets/images/slides/Slide30.JPG
<!-- .slide: data-transition="none" -->
@title[Locating library classes]
<p align="right"><span class="gold" >Locating Library Classes</span></p>

Note:

How do you find library classes?<br>
The simple answer is ”you have to know what the library class is based on.”
- For example, if it is based on industry standards like the UEFI, PI, SMBIOS, ACPI, etc…you are probably going to find it in the MDE package or maybe in the MDE module package. 

+++?image=/assets/images/slides/Slide31.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Locating library classes 02]
<p align="right"><span class="gold" >Locating Library Classes</span></p>

Note:

How do you find library classes?<br>
The simple answer is ”you have to know what the library class is based on.”
- For example, if it is based on industry standards like the UEFI, PI, SMBIOS, ACPI, etc…you are probably going to find it in the MDE package or maybe in the MDE module package. 



+++?image=/assets/images/slides/Slide32.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Locating library classes 03]
<p align="right"><span class="gold" >Locating Library Classes</span></p>

Note:

How do you find library classes?<br>
The simple answer is ”you have to know what the library class is based on.”
- For example, if it is based on industry standards like the UEFI, PI, SMBIOS, ACPI, etc…you are probably going to find it in the MDE package or maybe in the MDE module package. 



---?image=/assets/images/slides/Slide34.JPG
<!-- .slide: data-transition="none" -->
@title[Library Instance Hierarchy]
<p align="right"><span class="gold" >Library Instance Hierarchy</span></p>


Note:

+++?image=/assets/images/slides/Slide35.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Instance Hierarch 02]
<p align="right"><span class="gold" >Library Instance Hierarchy</span></p>

Note:


+++?image=/assets/images/slides/Slide36.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Instance Hierarch 03]
<p align="right"><span class="gold" >Library Instance Hierarchy</span></p>

Note:



+++?image=/assets/images/slides/Slide37.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Instance Hierarch 04]
<p align="right"><span class="gold" >Library Instance Hierarchy</span></p>

Note:


+++?image=/assets/images/slides/Slide38.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Instance Hierarch 05]
<p align="right"><span class="gold" >Library Instance Hierarchy</span></p>

Note:


+++?image=/assets/images/slides/Slide39.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Instance Hierarch 06]
<p align="right"><span class="gold" >Library Instance Hierarchy</span></p>

Note:



+++?image=/assets/images/slides/Slide40.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Instance Hierarch 07]
<p align="right"><span class="gold" >Library Instance Hierarchy</span></p>

Note:
- when the error Build : error 4000 : Instance of Library class [Foo…Lib] is not found in [WorkSpace/some module Lib.inf] consumed by module [WorkSpace/My Module.inf]


- Library Instances (NOT Library Classes) form a hierarchy similar to UEFI drivers
Some Library Instances will link your module to another Library DebugLib (Class)
- DebugLibSerialPort (Instance)
- SerialPort (Class)
- Etc…

The build process handles this, as long as a Library Instance is listed somewhere in the module hierarchy in the .DSC file


Library instances, not library classes, form a hierarchy very similar to the way drivers work.
One library instance you link to may link another library class without your awareness: 

For example, If you linked the debug Lib and then someone doing the platform decides that they will use the debug Lib serial port for your debug Lib class,
That debug serial port instance links against the serial Port library class which now links its own library instance.

Now the build will handle this all in the background. 
When it looks in your INF file it is going to see debug Lib, and when you look at the debug serial port it’s going to see serial port.  

As long as there is at least one of each library instance in the workspace and in DSC file, it will be built behind the scenes. You won’t even realize that there is more than one dependency under your module, and behind the scenes is doing this for everything. 
Another NOTE:  Most libraries are dependent on another library the same way that .c and .h files are dependent upon some other .c and .h files.. 


---?image=/assets/images/slides/Slide42.JPG
<!-- .slide: data-transition="none" -->
@title[Commonly Used Base Library Classes]
<p align="right"><span class="gold" >Commonly Used Base Library Classes</span></p>

Note:

Eye chart of many - MANY Many Libraries in the EDK II code

+++?image=/assets/images/slides/Slide43.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Commonly Used Base Library Classes 02]
<p align="right"><span class="gold" >Commonly Used Base Library Classes</span></p>

Note:

Eye chart of many - MANY Many Libraries in the EDK II code

+++?image=/assets/images/slides/Slide44.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Commonly Used Base Library Classes 03]
<p align="right"><span class="gold" >Commonly Used Base Library Classes</span></p>

Note:

Eye chart of many - MANY Many Libraries in the EDK II code

+++?image=/assets/images/slides/Slide45.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Commonly Used Base Library Classes 04]
<p align="right"><span class="gold" >Commonly Used Base Library Classes</span></p>

Note:

Eye chart of many - MANY Many Libraries in the EDK II code

+++?image=/assets/images/slides/Slide46.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Commonly Used Base Library Classes 05]
<p align="right"><span class="gold" >Commonly Used Base Library Classes</span></p>

Note:

Eye chart of many - MANY Many Libraries in the EDK II code

---?image=/assets/images/slides/Slide48.JPG
@title[MdePkg Library Doc. Location ]
<p align="right"><span class="gold" >MdePkg Library .CHM file Location </span></p>
<span style="font-size:0.8em" ><a href="https://github.com/tianocore/tianocore.github.io/wiki/UDK2018#documentation">tianocore.org UDK2018 Documentation </a>  on </span>
<br>
<br>
<div class="left1">
@fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/tianocore.github.io/wiki/UDK">Latest UDK Release </a>  </span><br><br><br>
@fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/tianocore.github.io/wiki/UDK2018">UDK2018</a></span><br>
</div>
<div class="right1">
   <p align="center"><span style="font-size:01.2em" ><font color="yellow"></font></span></p>
</div>

---?image=/assets/images/slides/Slide51.JPG
<!-- .slide: data-transition="none" -->
@title[Library Navigation Demonstration]
<p align="right"><span class="gold" >Library Navigation Demonstration</span></p>

Note:

- Install a CHM Viewer for Ubuntu

<pre>
bash$ sudo aptitude install kchmviewer
</pre>

chm file unlock – right click –properties –check unblock

+++?image=/assets/images/slides/Slide42.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Library Navigation Demonstration video]
<p align="right"><span class="gold" >Library Navigation Demonstration</span></p>
![video](https://www.youtube.com/embed/0DxaQBfKkTc)

Note:

- Install a CHM Viewer for Ubuntu

<pre>
bash$ sudo aptitude install kchmviewer
</pre>

chm file unlock – right click –properties –check unblock




---?image=assets/images/binary-strings-black2.jpg
@title[EDK II UEFI Applications Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EDK II UEFI Applications </span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>


---?image=/assets/images/slides/Slide54.JPG
@title[Defining a UEFI Application]
<p align="right"><span class="gold" >Defining a UEFI Application</span></p>
<span style="font-size:01.0em" ><font color="#92D050">Characteristics of a UEFI Loadable Image</font></span><br>
<br>
@ul[no-bullet]
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Loaded by UEFI loader, just like drivers</span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Does not register protocols </span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Consumes protocols</span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Typically exits when completed (user driven )</span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Same set of interfaces as drivers available</span> 
@ulend

Note:
@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;What is a EDK II Module</span><br>

UEFI Applications are just like UEFI drivers, they are loadable images. 

Their difference lies in that they typically do not register protocols like a driver does. They typically consume protocols to do a user driven task.

The same set of UEFI or firmware interfaces are available to applications that drivers have. Thus they are useful for driver prototyping since they can be quickly loaded from the UEFI shell to test the usage of an interface and help you in driver development.


- What do UEFI Applications do?
- Extend firmware abstractly
- Without hardware or OS dependence
- Portable across platforms 
- IA32, IA64, Intel-64, XScale, Apple*, NT32 emulator, OVMF emulator
- Enable rapid application development


---?image=/assets/images/slides/Slide56_1.JPG
@title[Defining a UEFI Application -Usages]
<p align="right"><span class="gold" >Defining a UEFI Application</span></p>
<span style="font-size:01.0em" ><font color="#92D050">UEFI Loadable Image Usages</font></span><br>
<br>
@ul[no-bullet]
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Diagnostics:  Platform / Factory  </span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Utilities </span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Driver Prototyping </span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;“Platform” Applications </span> 
- @fa[certificate gp-bullet-white]<span style="font-size:0.8em" >&nbsp;&nbsp;Portable Across Platforms (IA32, X64, ARM, Itanium, etc.) </span> 
@ulend

Note:
Their usages include factory testing, platform diagnostics (no OS required), and other various pre-boot applications you can think of where the need to do some operation without an OS would be useful.


---?image=/assets/images/slides/Slide58.JPG
<!-- .slide: data-transition="none" -->
@title[Executing Applications]
<p align="right"><span class="gold" >Executing Applications</span></p>


Note:

What are the Application Execution steps?

Applications written to the UEFI specification are loaded by the Boot Manager or by other UEFI
applications. For Example, the shell is an application . 

To load an application the firmware allocates enough memory to hold the image,
copies the sections within the application to the allocated memory, and applies the relocation fix-ups
needed. Once this is done, the allocated memory is set to be the proper type for code and data for the
image. Control is then transferred to the application’s entry point. When the application returns from
its entry point, or when it calls the Boot Service Exit(), the application is unloaded from memory
and control is returned to the UEFI component that loaded the application.


+++?image=/assets/images/slides/Slide59.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing Applications 02]
<p align="right"><span class="gold" >Executing Applications</span></p>


Note:

What are the Application Execution steps?

Applications written to the UEFI specification are loaded by the Boot Manager or by other UEFI
applications. For Example, the shell is an application . 

To load an application the firmware allocates enough memory to hold the image,
copies the sections within the application to the allocated memory, and applies the relocation fix-ups
needed. Once this is done, the allocated memory is set to be the proper type for code and data for the
image. Control is then transferred to the application’s entry point. When the application returns from
its entry point, or when it calls the Boot Service Exit(), the application is unloaded from memory
and control is returned to the UEFI component that loaded the application.




+++?image=/assets/images/slides/Slide60.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing Applications 03]
<p align="right"><span class="gold" >Executing Applications</span></p>


Note:

What are the Application Execution steps?

Applications written to the UEFI specification are loaded by the Boot Manager or by other UEFI
applications. For Example, the shell is an application . 

To load an application the firmware allocates enough memory to hold the image,
copies the sections within the application to the allocated memory, and applies the relocation fix-ups
needed. Once this is done, the allocated memory is set to be the proper type for code and data for the
image. Control is then transferred to the application’s entry point. When the application returns from
its entry point, or when it calls the Boot Service Exit(), the application is unloaded from memory
and control is returned to the UEFI component that loaded the application.



+++?image=/assets/images/slides/Slide61.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing Applications 04]
<p align="right"><span class="gold" >Executing Applications</span></p>


Note:

What are the Application Execution steps?

Applications written to the UEFI specification are loaded by the Boot Manager or by other UEFI
applications. For Example, the shell is an application . 

To load an application the firmware allocates enough memory to hold the image,
copies the sections within the application to the allocated memory, and applies the relocation fix-ups
needed. Once this is done, the allocated memory is set to be the proper type for code and data for the
image. Control is then transferred to the application’s entry point. When the application returns from
its entry point, or when it calls the Boot Service Exit(), the application is unloaded from memory
and control is returned to the UEFI component that loaded the application.



+++?image=/assets/images/slides/Slide62.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing Applications 05]
<p align="right"><span class="gold" >Executing Applications</span></p>


Note:

What are the Application Execution steps?

Applications written to the UEFI specification are loaded by the Boot Manager or by other UEFI
applications. For Example, the shell is an application . 

To load an application the firmware allocates enough memory to hold the image,
copies the sections within the application to the allocated memory, and applies the relocation fix-ups
needed. Once this is done, the allocated memory is set to be the proper type for code and data for the
image. Control is then transferred to the application’s entry point. When the application returns from
its entry point, or when it calls the Boot Service Exit(), the application is unloaded from memory
and control is returned to the UEFI component that loaded the application.

---?image=/assets/images/slides/Slide65.JPG
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App]
<p align="right"><span class="gold" >Executing Applications</span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide66.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 02]
<p align="right"><span class="gold" >Executing Applications</span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide67.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 03]
<p align="right"><span class="gold" >Executing Applications</span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide68.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 04]
<p align="right"><span class="gold" >Executing Applications</span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide69.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 05]
<p align="right"><span class="gold" >Executing Applications</span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide70.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 06]
<p align="right"><span class="gold" >Executing Applications</span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over



---?image=/assets/images/slides/Slide73.JPG
<!-- .slide: data-transition="none" -->
@title[Driver vs. Application]
<p align="right"><span class="gold" >Driver Vs. Application</span></p>

Note:


+++?image=/assets/images/slides/Slide74.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Driver vs. Application 02]
<p align="right"><span class="gold" >Driver Vs. Application</span></p>

Note:


+++?image=/assets/images/slides/Slide75.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Driver vs. Application 03]
<p align="right"><span class="gold" >Driver Vs. Application</span></p>

Note:


---?image=assets/images/binary-strings-black2.jpg
@title[Writing EDK II Applications Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EDK II UEFI Applications </span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;How to Write a EDK II UEFI Application</span>


---?image=/assets/images/slides/Slide78.JPG
<!-- .slide: data-transition="none" -->
@title[Application Files Placement]
<p align="right"><span class="gold" >Application Files Placement</span></p>

Note:
Same as slide



+++?image=/assets/images/slides/Slide79.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Application Files Placement 02]
<p align="right"><span class="gold" >Application Files Placement</span></p>

Note:
Same as slide


+++?image=/assets/images/slides/Slide80.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Application Files Placement 03]
<p align="right"><span class="gold" >Application Files Placement</span></p>

Note:
Same as slide


+++?image=/assets/images/slides/Slide81.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Application Files Placement 04]
<p align="right"><span class="gold" >Application Files Placement</span></p>

Note:
Same as slide


---?image=/assets/images/slides/Slide83.JPG
@title[Module .INF File]
<p align="right"><span class="gold" >Module .INF File</span></p><br>
<span style="font-size:01.1em" ><font color="yellow">Syntax</font></span>
<br>
<br>
<br>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/blob/master/MdeModulePkg/Application/VariableInfo/VariableInfo.inf">INF text file example </a></span>

Note:

Update to define all Sources (.c, .h, .uni) , libraries, Packages, Guids,  PCDs be used by the Module

See EDK II INF  File Specification for more details and examples

1 Depex only used with specific Module types


---?image=/assets/images/slides/Slide85.JPG
@title[Application INF Files -DEFINES]
<p align="right"><span class="gold" >Application INF Files [DEFINES]</span></p>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<span style="font-size:0.5em" ><font color="yellow">*EDK II Specifications: </font> <a href="https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications">https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications </a></span>

Note:

- There are other optional fields
- Check the Extended INF Specification

#### defines
- INF_VERSION 1.25* - Version of the INF spec.
- BASE_NAME What’s the name of the application
- FILE_GUID Create a GUID for your module
- MODULE_UNI_FILE Meta-data - localization for Description & Abstract
- VERSION_STRING Version number
- ENTRY_POINT Name of the function to call
- MODULE_TYPE UEFI_APPLICATION

---
<!-- .slide: data-background-transition="none" -->
@title[Sample INF file]
<p align="right"><span class="gold" >Sample INF file</span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  FILE_GUID                      = 215cdcfb-1cfc-47e0-9c02-47048c21d20d
  MODULE_TYPE                    = UEFI_APPLICATION
  VERSION_STRING                 = 1.0
  ENTRY_POINT                    = UefiMain

[Sources]
  MyFile.c

[Packages]
  MdePkg/MdePkg.dec
  
[LibraryClasses]
  UefiApplicationEntryPoint
    
[Guids]

[Ppis]

[Protocols]

```

Note:

+++
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Sample INF file]
<p align="right"><span class="gold" >Sample INF file</span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  FILE_GUID                      = 215cdcfb-1cfc-47e0-9c02-47048c21d20d
  MODULE_TYPE                    = UEFI_APPLICATION
  VERSION_STRING                 = 1.0
  ENTRY_POINT                    = UefiMain

[Sources]
  MyFile.c

[Packages]
  MdePkg/MdePkg.dec
  
[LibraryClasses]
  UefiApplicationEntryPoint
    
[Guids]

[Ppis]

[Protocols]

```

@[1-7](Defines for this .INF file; BASE_NAME results in this name.efi file)
@[9-10]( Source: .c, .h, .uni, .vfr, any files needed for the compiler/linker/lib etc)
@[12-16](Package dependencies and Libraries this module will include in its final binary image)

Note:

---?image=/assets/images/slides/Slide88.JPG
@title[Building an Application]
#### <p align="right"><span class="gold" >Building an Application</span></p>
<br>
<br>
<span style="font-size:01.1em" ><font color="cyan"> Platform .DSC references .INF </font></span>
<div class="left2">
<ul style="list-style-type:none">
  <li><span style="font-size:0.9em" ><font color="yellow">Runs:</font></span><br></li>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp;&nbsp;“Build” for the entire platform     </span>
  <li><span style="font-size:0.9em" ><font color="yellow">&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; OR</font></span></li>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp;&nbsp;“Build” in the application’s directory    </span></li>
</ul>
</div>
<div class="right2">
   <p align="center"><span style="font-size:01.2em" ><font color="yellow"></font></span></p>
</div>

Note:
- Put the INF file in the components section withinin DSC file
- Platform references .INF file
- Provides context for the application to build within
- You can build an app without building the entire platform
- The DSC for the platform must reference the INF
- Run “build” for the entire platform
- Run “build” in the application’s directory
- Will build any required files (libs, etc…)


---
<!-- .slide: data-transition="none" -->
@title[Sample Application "C" File]
<p align="right"><span class="gold" >Sample Application "C" File</span></p>
<br>
<br>
```C
#include <Uefi.h>
#include <Library/UefiApplicationEntryPoint.h>


EFI_STATUS
EFIAPI
UefiMain (
  IN EFI_HANDLE        ImageHandle,
  IN EFI_SYSTEM_TABLE  *SystemTable
  )
{
  return EFI_SUCCESS;
}
```


Note:
This sample application does not do anything, it is just a reference.


+++
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Sample Application "C" File]
<p align="right"><span class="gold" >Sample Application "C" File</span></p>
<br>
<br>
```C
#include <Uefi.h>
#include <Library/UefiApplicationEntryPoint.h>


EFI_STATUS
EFIAPI
UefiMain (
  IN EFI_HANDLE        ImageHandle,
  IN EFI_SYSTEM_TABLE  *SystemTable
  )
{
  return EFI_SUCCESS;
}
```

@[7]( The function name is the same as in the .inf file "ENTRY_POINT" define)
@[8-9](Parameters passed to EVERY UEFI entry point: Handle to "itself" AKA "this", EFI_SYSTEM_TABLE, a pointer to <b>Everything</b> in the system)
@[12]( This function does not really do anything but return "success", EFI_SUCCESS = 0)


Note:
This sample application does not do anything, it is just a reference.



---?image=/assets/images/slides/Slide91.JPG
@title[UEFI Application Vs. EADK Application]
<p align="right"><span class="gold" >UEFI Application Vs. EADK Application</span></p>
<br>
<br>
<div class="left1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" ><font color="yellow">EDK II Application Development Kit includes the Standard C Libraries in UEFI Shell Applications
</font></span><br></li><br>
  <li><span style="font-size:0.8em" ><font color="yellow"><i>Off the shelf</i> “C” application Converted to UEFI application 
</font></span></li>
</ul>
</div>
<div class="right1">
   <p align="center"><span style="font-size:01.2em" ><font color="yellow"></font></span></p>
</div>

Note:
- EDK II Application Development Kit includes the Standard C Libraries in UEFI Shell Applications
- Off the shelf “C” application Converted to UEFI application 



---
<!-- .slide: data-transition="none" -->
@title[Sample INF file using EDK II EADK ]
<p align="right"><span class="gold" >Sample INF file using EDK II EADK</span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  FILE_GUID                      = 215cdcfb-1cfc-47e0-9c09-47048c21d20d
  MODULE_TYPE                    = UEFI_APPLICATION
  VERSION_STRING                 = 1.0
  ENTRY_POINT                    = ShellCEntryLib

[Sources]
  MyFile.c

[Packages]
  StdLib/StdLib.dec
  ShellPkg/ShellPkg.dec
  MdePkg/MdePkg.dec
  
[LibraryClasses]
  LibC
  LibStdio
    
[Guids]

[Ppis]

[Protocols]
```

Note:

#### Differences: 
- ENTRY_POINT                    = ShellCEntryLib
- [Packages]
  -   StdLib/StdLib.dec
  -   ShellPkg/ShellPkg.dec

- [LibraryClasses]
  -   LibC
  - LibStdio


  
+++
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Sample INF file using EDK II EADK ]
<p align="right"><span class="gold" >Sample INF file using EDK II EADK</span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  FILE_GUID                      = 215cdcfb-1cfc-47e0-9c09-47048c21d20d
  MODULE_TYPE                    = UEFI_APPLICATION
  VERSION_STRING                 = 1.0
  ENTRY_POINT                    = ShellCEntryLib

[Sources]
  MyFile.c

[Packages]
  StdLib/StdLib.dec
  ShellPkg/ShellPkg.dec
  MdePkg/MdePkg.dec
  
[LibraryClasses]
  LibC
  LibStdio
    
[Guids]

[Ppis]

[Protocols]
```
@[7]( Entry point is a library in the shell to get parameters from the command line)
@[12-14]( Packages included for standard "C" lib and Shell Lib)
@[17-19]( Library classes for ANSI "C" and Standard IO "stdio.h")

Note:

#### Differences: 
- ENTRY_POINT                    = ShellCEntryLib
- [Packages]
  -   StdLib/StdLib.dec
  -   ShellPkg/ShellPkg.dec

- [LibraryClasses]
  -   LibC
  - LibStdio
  

---
@title[Sample "C" file using EDK II EADK ]
<p align="right"><span class="gold" >Sample "C" file using EDK II EADK</span></p>
<br>
<span style="font-size:0.9em" >This sample looks a lot like actual “C” source.</span>


```C 
#include <stdio.h>


  int
  Main (
    IN int Argc,
    IN char **Argv
    )
  {
    return 0;
  }
```

Note:

simple "C" looks like a normal "C" file  
  

---?image=/assets/images/slides/Slide96.JPG
<!-- .slide: data-transition="none" -->
@title[Driver File Placement]
<p align="right"><span class="gold" >Driver File Placement</span></p>

Note:
Same as slide


+++?image=/assets/images/slides/Slide97.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Driver File Placement 02]
<p align="right"><span class="gold" >Driver File Placement</span></p>

Note:
Same as slide


+++?image=/assets/images/slides/Slide98.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Driver File Placement 03]
<p align="right"><span class="gold" >Driver File Placement</span></p>

Note:
Same as slide


+++?image=/assets/images/slides/Slide99.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Driver File Placement 04]
<p align="right"><span class="gold" >Driver File Placement</span></p>

Note:
Same as slide

---?image=/assets/images/slides/Slide101.JPG
@title[Driver INF Files: DEFINES]
<p align="right"><span class="gold" >Driver INF Files: [DEFINES]</span></p>


Note:
- There are other optional fields
- Check the Extended INF Specification
- Notice the differences between Application and driver is only the MODULE_TYPE - so simply change the module type and it becomes a driver.

#### defines
- INF_VERSION 1.25* - Version of the INF spec.
- BASE_NAME What’s the name of the DRIVER
- FILE_GUID Create a GUID for your module
- MODULE_UNI_FILE Meta-data - localization for Description & Abstract
- VERSION_STRING Version number
- ENTRY_POINT Name of the function to call
- MODULE_TYPE UEFI_DRIVER, DXE_DRIVER, PEIM, or others

---?image=/assets/images/slides/Slide103.JPG
<!-- .slide: data-transition="none" -->
@title[Changes for a UEFI Driver Module]
<p align="right"><span class="gold" >Changes for a UEFI Driver Module</span></p>

Note:
same as slide

+++?image=/assets/images/slides/Slide104.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Changes for a UEFI Driver Module 02]
<p align="right"><span class="gold" >Changes for a UEFI Driver Module</span></p>

Note:
same as slide


+++?image=/assets/images/slides/Slide105.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Changes for a UEFI Driver Module 03]
<p align="right"><span class="gold" >Changes for a UEFI Driver Module</span></p>

Note:
same as slide
+++?image=/assets/images/slides/Slide106.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Changes for a UEFI Driver Module 04]
<p align="right"><span class="gold" >Changes for a UEFI Driver Module</span></p>

Note:
same as slide
 


---
<!-- .slide: data-transition="none" -->
@title[Sample INF Driver file]
<p align="right"><span class="gold" >Sample Driver INF file</span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyDriver
  FILE_GUID                      = 215cdcfb-1cfc-47e0-9c02-92d05021d20d
  MODULE_TYPE                    = UEFI_DRIVER
  VERSION_STRING                 = 1.0
  ENTRY_POINT                    = UefiMain

[Sources]
  MyFile.c

[Packages]
  MdePkg/MdePkg.dec
  
[LibraryClasses]
  UefiDriverEntryPoint
    
[Guids]

[Ppis]

[Protocols]

```

@[4](Always get a new GUID - http://www.guidgen.com )
@[5](UEFI_DRIVER instead of Application)
@[15-16](Library for Driver instead of Application)

Note:


  
---?image=/assets/images/slides/Slide109.JPG
@title[INF Usage fields – DIST files ]
<p align="right"><span class="gold" >INF Usage fields – DIST files </span></p>


Note:

- CONSUMES
  - This module does not install the protocol, but needs to locate a protocol. Not valid if the Notify attribute is true.
- PRODUCES
  - This module will install this protocol. Not valid if the Notify attribute is true.
- SOMETIMES_CONSUMES
  - This module does not install the protocol, but may need to locate a protocol under certain conditions, (such as if it is present.) If the Notify attribute is set, then the module will use the protocol, named by GUID, via a registry protocol notify mechanism.
- SOMETIMES_PRODUCES
  - This module will install this protocol under certain conditions. Not valid if the Notify attribute is true.
- TO_START
  - The protocol is consumed by a Driver Binding protocol Start function. Thus the protocol is used as part of the UEFI driver model. Not valid if the Notify attribute is true.
- BY_START
  - The protocol is produced by a Driver Binding protocol Start function. Thus the protocol is used as part of the UEFI driver model. Not valid if the Notify attribute is true.
- NOTIFY
  - This specifies whether this is a Protocol or ProtocolNotify. If set, then the module will use this protocol, named by GUID, via a registry protocol notify mechanism.
- UNDEFINED
  - Typically, this entry will be used when tools creating/installing UEFI Distribution Packages encounter a missing or misspelled usage. UNDEFINED is also valid when the Protocol is not used as a Protocol and the GUID value of the Protocol is used for something else.


---
@title[INF File Usage Block examples]
<p align="right"><span class="gold" >INF File Usage Block examples</span></p>
<br>

<pre>
```

[Guids]
  ## SOMETIMES_PRODUCES ## Variable:L"ConInDev"
  ## SOMETIMES_CONSUMES ## Variable:L"ConInDev"
  ## SOMETIMES_PRODUCES ## Variable:L"ConOutDev"
  ## SOMETIMES_CONSUMES ## Variable:L"ConOutDev"
  ## SOMETIMES_PRODUCES ## Variable:L"ErrOutDev"
  ## SOMETIMES_CONSUMES ## Variable:L"ErrOutDev"
  gEfiGlobalVariableGuid
  gEfiVTUTF8Guid                                ## SOMETIMES_CONSUMES ## GUID # used with a Vendor-Defined Messaging Device Path
  gEfiVT100Guid                                 ## SOMETIMES_CONSUMES ## GUID # used with a Vendor-Defined Messaging Device Path
  gEfiVT100PlusGuid                             ## SOMETIMES_CONSUMES ## GUID # used with a Vendor-Defined Messaging Device Path
  gEfiPcAnsiGuid                                ## SOMETIMES_CONSUMES ## GUID # used with a Vendor-Defined Messaging Device Path
  gEfiTtyTermGuid                               ## SOMETIMES_CONSUMES ## GUID # used with a Vendor-Defined Messaging Device Path
  gEdkiiStatusCodeDataTypeVariableGuid          ## SOMETIMES_CONSUMES ## GUID

```
</pre>

@[1-8](The Usage Block text comes before the `gEfiGlobalVariableGuid' GUID)
@[9-14](The Usage Block text comes after the referenced GUIDs)

<p align="right"><span style="font-size:0.7em" >Example: <a href="https://github.com/tianocore/edk2/blob/master/MdeModulePkg/Universal/Console/TerminalDxe/TerminalDxe.inf">TerminalDxe.inf </a></span> </p>

Note:

- CONSUMES
  - This module does not install the protocol, but needs to locate a protocol. Not valid if the Notify attribute is true.
- PRODUCES
  - This module will install this protocol. Not valid if the Notify attribute is true.
- SOMETIMES_CONSUMES
  - This module does not install the protocol, but may need to locate a protocol under certain conditions, (such as if it is present.) If the Notify attribute is set, then the module will use the protocol, named by GUID, via a registry protocol notify mechanism.
- SOMETIMES_PRODUCES
  - This module will install this protocol under certain conditions. Not valid if the Notify attribute is true.
- TO_START
  - The protocol is consumed by a Driver Binding protocol Start function. Thus the protocol is used as part of the UEFI driver model. Not valid if the Notify attribute is true.
- BY_START
  - The protocol is produced by a Driver Binding protocol Start function. Thus the protocol is used as part of the UEFI driver model. Not valid if the Notify attribute is true.
- NOTIFY
  - This specifies whether this is a Protocol or ProtocolNotify. If set, then the module will use this protocol, named by GUID, via a registry protocol notify mechanism.
- UNDEFINED
  - Typically, this entry will be used when tools creating/installing UEFI Distribution Packages encounter a missing or misspelled usage. UNDEFINED is also valid when the Protocol is not used as a Protocol and the GUID value of the Protocol is used for something else.

  

+++
@title[INF File Usage Block examples]
<p align="right"><span class="gold" >INF File Usage Block examples</span></p>
<br>

<pre>
```

[Protocols]
  gEfiSerialIoProtocolGuid                      ## TO_START
  ## BY_START
  ## TO_START
  gEfiDevicePathProtocolGuid
  gEfiSimpleTextInProtocolGuid                  ## BY_START
  gEfiSimpleTextInputExProtocolGuid             ## BY_START
  gEfiSimpleTextOutProtocolGuid                 ## BY_START

[Pcd]
  gEfiMdePkgTokenSpaceGuid.PcdDefaultTerminalType           ## SOMETIMES_CONSUMES
  gEfiMdeModulePkgTokenSpaceGuid.PcdErrorCodeSetVariable    ## CONSUMES
```
</pre>

@[3-5](The Usage Block text comes before the `gEfiDevicePathProtocolGuid' protocol GUID)
@[7-12](The Usage Block text comes after the referenced protocol GUIDs and PCDs)

<p align="right"><span style="font-size:0.7em" >Example: <a href="https://github.com/tianocore/edk2/blob/master/MdeModulePkg/Universal/Console/TerminalDxe/TerminalDxe.inf">TerminalDxe.inf </a></span> </p>

Note:

- CONSUMES
  - This module does not install the protocol, but needs to locate a protocol. Not valid if the Notify attribute is true.
- PRODUCES
  - This module will install this protocol. Not valid if the Notify attribute is true.
- SOMETIMES_CONSUMES
  - This module does not install the protocol, but may need to locate a protocol under certain conditions, (such as if it is present.) If the Notify attribute is set, then the module will use the protocol, named by GUID, via a registry protocol notify mechanism.
- SOMETIMES_PRODUCES
  - This module will install this protocol under certain conditions. Not valid if the Notify attribute is true.
- TO_START
  - The protocol is consumed by a Driver Binding protocol Start function. Thus the protocol is used as part of the UEFI driver model. Not valid if the Notify attribute is true.
- BY_START
  - The protocol is produced by a Driver Binding protocol Start function. Thus the protocol is used as part of the UEFI driver model. Not valid if the Notify attribute is true.
- NOTIFY
  - This specifies whether this is a Protocol or ProtocolNotify. If set, then the module will use this protocol, named by GUID, via a registry protocol notify mechanism.
- UNDEFINED
  - Typically, this entry will be used when tools creating/installing UEFI Distribution Packages encounter a missing or misspelled usage. UNDEFINED is also valid when the Protocol is not used as a Protocol and the GUID value of the Protocol is used for something else.

  
  
  

---?image=/assets/images/slides/Slide112_1.JPG
@title[UEFI Driver Example - Disk I/O]
<p align="right"><span class="gold" >UEFI Driver Example - Disk I/O</span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a></span><br>

Note:
- PCI Platform DXE
- Under workspace directory
- Under the Platform Package

---
@title[UEFI Driver Example - Disk I/O]
<p align="right"><span class="gold" >UEFI Driver Example - Disk I/O</span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a>- entry point</span><br>
<div class="left2">
<span style="font-size:0.8em" ><font color="cyan">"C" file</font></span>
<pre>
```
EFI_STATUS
EFIAPI
InitializeDiskIo (
  IN EFI_HANDLE           ImageHandle,
  IN EFI_SYSTEM_TABLE     *SystemTable
)
  // . . .
  Status = EfiLibInstallDriverBindingComponentName2 (
             ImageHandle,
             SystemTable,
             &gDiskIoDriverBinding,
             ImageHandle,
             &gDiskIoComponentName,
             &gDiskIoComponentName2
             );
  ASSERT_EFI_ERROR (Status);
  return Status;
}
```
</pre>
@[3](Entry point for this UEFI Driver)
@[8-11](Install -Supported, Start and Stop for the UEFI Driver binding protocol)
@[3-17](The UEFI Driver Only does the <b>Install</b> then EXITs)
</div>
<div class="right2">
<span style="font-size:0.8em" ><font color="yellow">INF file</font></span>
<pre>
```
[Defines]
 . . .
  ENTRY_POINT  = InitializeDiskIo
```
</pre>
</div>

Note:



---
@title[UEFI Driver Example - Disk I/O 02]
<p align="right"><span class="gold" >UEFI Driver Example - Disk I/O</span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a>- Supported </span><br>

<div class="left2">
<span style="font-size:0.8em" ><font color="cyan">"C" file</font></span>
<pre>
```
EFI_STATUS
EFIAPI
DiskIoDriverBindingSupported (
  IN EFI_DRIVER_BINDING_PROTOCOL  *This,
  IN EFI_HANDLE                   ControllerHandle,
  IN EFI_DEVICE_PATH_PROTOCOL     *RemainingDevicePath OPTIONAL
  )
{
  Status = gBS->OpenProtocol (
	ControllerHandle,
      &gEfiBlockIoProtocolGuid,
      (VOID **) &BlockIo,
	  This->DriverBindingHandle,
	  ControllerHandle,
	  EFI_OPEN_PROTOCOL_BY_DRIVER
	);
	
```
</pre>
@[3](Entry point for Supported)
@[11]( Using the global gEfiBlockIoProtocolGuid protocol to determine if this device controller handle is a Block I/O device)
</div>
<div class="right2">
<span style="font-size:0.8em" ><font color="yellow">INF file</font></span>
<pre>
```
[Protocols]
  . . .
  gEfiBlockIoProtocolGuid  ## TO_START
```
</pre>
</div>

Note:

Using the global gEfiBlockIoProtocolGuid protocol to determine if this device controller handle is a Block I/O device

---
@title[UEFI Driver Example - Disk I/O 03]
<p align="right"><span class="gold" >UEFI Driver Example - Disk I/O</span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a>- Start</span><br>

<div class="left2">
<span style="font-size:0.8em" ><font color="cyan">"C" file</font></span>
<pre>
```
EFI_STATUS
EFIAPI
 DiskIoDriverBindingStart (
  IN EFI_DRIVER_BINDING_PROTOCOL  *This,
  IN EFI_HANDLE                   ControllerHandle,
  IN EFI_DEVICE_PATH_PROTOCOL     *RemainingDevicePath OPTIONAL
  )
{

  if (Instance->BlockIo2 != NULL) {
    Status = gBS->InstallMultipleProtocolInterfaces (
	&ControllerHandle,
	&gEfiDiskIoProtocolGuid,  &Instance->DiskIo,
	&gEfiDiskIo2ProtocolGuid, &Instance->DiskIo2,
	NULL	
	);
	
```
</pre>
@[3](Entry point for Start function)
@[13-14]( Using the global gEfiDiskIoProtocolGuid and gEfiDiskIo2ProtocolGuid protocols to INSTALL handles to)
</div>
<div class="right2">
<span style="font-size:0.8em" ><font color="yellow">INF file</font></span>
<pre>
```
[Protocols]
  . . .
  gEfiDiskIoProtocolGuid   ## BY_START
  gEfiDiskIo2ProtocolGuid  ## BY_START

```
</pre>
</div>

Note:



---?image=/assets/images/slides/Slide117_1.JPG
@title[DXE Driver Example - PlatformInfoDxe]
<p align="right"><span class="gold" >DXE Driver Example - PlatformInfoDxe</span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2-platforms/tree/devel-MinnowBoardMax-UDK2017/Vlv2TbltDevicePkg/PlatformInfoDxe">https://github.com/tianocore/edk2-platforms/ PlatformInfoDxe</a></span><br>

Note:
- PCI Platform DXE
- Under workspace directory
- Under the Platform Package



---
@title[DXE Example .INF File - PlatformInfoDxe]
<p align="right"><span class="gold" >DXE Driver Example - PlatformInfoDxe</span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2-platforms/tree/devel-MinnowBoardMax-UDK2017/Vlv2TbltDevicePkg/PlatformInfoDxe">https://github.com/tianocore/edk2-platforms/ PlatformInfoDxe</a></span><br>
<span style="font-size:0.6em"  >Notice the MODULE TYPE, C function Entry point and the [Depex] differences in the INF file </span>
<div class="left1">
<span style="font-size:0.8em" ><font color="cyan">"C" file</font></span>
<pre>
```
#include “PlatformInfoDxe.h“
• • •
EFI_STATUS
EFIAPI
PlatformInfoInit (
  IN EFI_HANDLE        ImageHandle,
  IN EFI_SYSTEM_TABLE  *SystemTable
  )
/*++
{
// • • •
  return Status;
}
```
</pre>
</div>

<div class="right1">
<span style="font-size:0.8em" ><font color="yellow">INF file</font></span>
<pre>
```
[Defines]
 . . .
  MODULE_TYPE     = DXE_DRIVER
  VERSION_STRING  = 1.0
  ENTRY_POINT     = PlatformInfoInit
 . . .

[Depex]
  gEfiVariableArchProtocolGuid AND 
    gEfiVariableWriteArchProtocolGuid
```
</pre>
</div>


Note:

MODULE_TYPE         = DXE_DRIVER

Depex section is part of the Dxe driver INF file

---?image=/assets/images/slides/Slide121_1.JPG
@title[PEI Driver (PEIM) Example - CpuIoPei]
<p align="right"><span class="gold" >PEI Driver (PEIM) Example - CpuIoPei</span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/UefiCpuPkg/CpuIoPei">https://github.com/tianocore/edk2/ UefiCpuPkg/CpuIoPei  </a> </span>

Note:
- PCI Platform DXE
- Under workspace directory
- Under the Platform Package


---
@title[PEI Driver (PEIM) Example - CpuIoPei]
<p align="right"><span class="gold" >PEI Driver (PEIM) Example - CpuIoPei</span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/UefiCpuPkg/CpuIoPei">https://github.com/tianocore/edk2/ UefiCpuPkg/CpuIoPei  </a> </span>
<div class="left1">
<span style="font-size:0.8em" ><font color="cyan">"C" file</font></span>
<pre>
```
#include “CpuIoPei.h“
 //• • •
EFI_STATUS
EFIAPI
CpuIoInitialize (
  IN EFI_PEI_FILE_HANDLE     FileHandle,
  IN CONST EFI_PEI_SERVICES  **PeiServices
  )
{
  EFI_STATUS  Status;
 //• • •
  return EFI_SUCCESS;
}
```
</pre>
@[5](Entry point for this Dxe Driver)
@[6-7]("FileHandle" - Instead of the ImageHandle & NO EFI_SYSTEM_TABLE - Not yet defined)

</div>
<div class="right1">
<span style="font-size:0.8em" ><font color="yellow">INF file</font></span>
<pre>
```
[Defines]
 . . .
  MODULE_TYPE       = PEIM
  VERSION_STRING    = 1.0  
  ENTRY_POINT       = CpuIoInitialize
 . . .

[Depex]
   TRUE
```
</pre>
</div>

Note:

- INF file Module type PEIM

- "FileHandle" - Instead of the ImageHandle & 
- NO EFI_SYSTEM_TABLE - because it is Not yet defined so pointer to the PEI Services is uses similar to EFI System table

---  
@title[Summary]
<BR>
### <p align="center"><span class="gold"   >Summary </span></p><br>
<br>
 @fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;What is a EDK II Module</span><br>
 @fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Use EDK II libraries to write UEFI apps/drivers</span><br>
 @fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;How to Define a UEFI application</span> <br>
 @fa[certificate gp-bullet-magenta]<span style="font-size:0.9em">&nbsp;&nbsp;Differences between UEFI App / Drivers INF file</span><br>

 

---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/questions.JPG) 


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

Copyright (c) 2018, Intel Corporation. All rights reserved.
**/

```
