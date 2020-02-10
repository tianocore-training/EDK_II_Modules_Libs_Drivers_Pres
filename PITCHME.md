---?image=assets/images/gitpitch-audience.jpg
@title[EDK II Modules]
<br><br><br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### EDK II Modules: Libs, Drivers & Apps

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  EDK II Modules: Libs, Drivers & Apps Pres

  Copyright (c) 2020, Intel Corporation. All rights reserved.<BR>

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
@title[Modules]
### <p align="right"><span class="gold" >Modules</span></p>
@css[text-white fragment](<b> Smallest separate object compiled in EDK II</b>)
<br>
<br>
<br>
@css[text-yellow fragment](<b>@color[yellow](Compiles to)<br>@color[yellow](<font face="Consolas">.EFI File</fon>)</b>)


@snap[east span-35]
@css[ text-white fragment](<b>UEFI/DXE Driver <br>@color[yellow](PEIM)<br>@color[orange](UEFI App.) </b>or <b><br>@color[#00ffff](Library) </b>)
@snapend

@snap[south span-90 fragment]
@box[bg-purple-pp-trans text-white  rounded](<b>Modules: &nbsp;&nbsp;Building Blocks of EDK II</b>)
@snapend

Note:

So the first thing we have in trying to break EDK II down is Modules:
 
- A module is the smallest separate object compiled in the EDK II.  A module is a single resultant .EFI file.
- Module examples:
- A UEFI/DXE driver 
- A PEIM
- A UEFI application
- A Library 

- All of these could be a module.  A modules could  be one entity



 
---
@title[Module Types]
### <p align="right"><span class="gold" >Module Types</span></p>
@snap[north span-60 fragment]
<br>
<br>
<br>
@box[bg-purple-pp text-white ](<span style="font-size:01.20em" ><b>Most Used Module Types</b></span>)
@snapend

@snap[north-west span-100 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p align="left" style="line-height:80%"><span style="font-size:0.9em; font-weight: bold;" >
@color[#00b0f0](<font face="Consolas">PEI_CORE</font>) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @color[yellow](<font face="Consolas">UEFI_APPLICATION</font>) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @color[orange](<font face="Consolas">DXE_CORE</font>)<br><br>
@color[orange](<font face="Consolas">BASE</font>) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @color[#00b0f0](<font face="Consolas">DXE_RUNTIME_DRIVER</font>) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <br><br>
@color[#87E2A9](<font face="Consolas">PEIM</font>) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @color[yellow](<font face="Consolas">UEFI_DRIVER</font>) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; @color[#87E2A9](<font face="Consolas">DXE_DRIVER</font>)<br>
</span></p>

@snapend

@snap[south span-100 fragment]
<p align="left" style="line-height:80%"><span style="font-size:0.65em"><i>syntax:</i></span><br>
<span style="font-size:0.65em; font-family: Courier New; color: yellow; font-weight: bold; background-color: #0d0d0d" > 
&lt;ModuleTypes&gt;&nbsp; ::= &nbsp;&lt;ModuleType&gt; [&lt;Space&gt; &lt;ModuleType&gt;]
</span> </p>
@snapend


@snap[north-west span-90 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:20%"><span style="font-size:0.65em"><br><br><br><br><br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>
<span style="font-size:02.65em">@color[red](&DDotrahd;)</span></p>
@snapend

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

There are many Module types.  This also determines how the module code is compiled and how libraries are associated with each module.

the syntax is: as shown on the slide

First we will show the UEFI_APPLICATION type of module since it is the simplest and can be somewhat independent from the underlining hardware.



---
@title[Module Source - minimum files]
<p align="right"><span class="gold" ><b>Module Source Contents </b></span><span style="font-size:0.8em" >- minimum files</span></p>
<table id="recTable2">
	<tr>
		<td bgcolor="#121212" height=".025"><p style="line-height:010%"><span style="font-size:0.8em" ><b>MODULE_TYPE</b></span></p></td>
		<td bgcolor="#121212" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.8em" ><b>Example Source files </b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">UEFI_APPLICATION</font></b></span></p></td>
		<td  bgcolor="#404040" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.65em" >@color[yellow](<b><font face="Consolas">Foo.c, Foo.inf </font></b>)</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">UEFI_DRIVER</font></b></span></p></td>
		<td  bgcolor="#404040" height=".025" width="70%"><p style="line-height:050%"><span style="font-size:0.65em" >@color[yellow](<b><font face="Consolas">FooDriver.c, FooDriver.h, FooDriver.vfr,</font><br><font face="Consolas">FooDriver.uni, FooDriver.inf </font></b>)</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">DXE_DRIVER</font></b></span></p></td>
		<td  bgcolor="#404040" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.65em" >@color[yellow](<b><font face="Consolas">FooDxe.c, FooDxe.h, FooDxe.inf</font></b>)</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".025"><p style="line-height:050%"><span style="font-size:0.65em" ><b>DXE, UEFI or PEIM Library</b></span></p></td>
		<td  bgcolor="#404040" height=".025" width="70%"><p style="line-height:050%"><span style="font-size:0.65em" >@color[yellow](<b><font face="Consolas">FooLib.c, FooLib.h, FooLib.inf </font></b>)&nbsp;&nbsp; ( w/ <font face="Consolas">LIBRARY_CLASS=</font> )</span></p></td>
	</tr>

</table>
@snap[south-west span-100]
@box[bg-brick-trans text-white rounded fragment ](<span style="font-size:01.20em" ><b>Complexity - Greater number of source files</b></span>)
@box[bg-lt-orange-trans text-white rounded fragment ](<span style="font-size:01.20em" ><b>.INF file - One file is required per module</b></span>)
@box[bg-gold2-trans text-white rounded fragment ](<span style="font-size:01.20em" ><b>.EFI file - Sources compiled to a single .EFI file</b></span>)
@snapend

Note:

Example of the naming and number of files associated with the modules types

- the number of files is based on the Complexity of the UEFI / DXE driver and or UEFI application
- There is a requirement that a module must have at least 1 .INF file
- The resulting compilation will be a .EFI file 


---?image=assets/images/binary-strings-black2.jpg
@title[EDK II Library Modules Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EDK II Library Modules</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>


---
@title[Library Class ]
<p align="right"><span class="gold" ><b>Library Class</b></span></p>
<span style="font-size:0.85em"><b><i>Syntax:</i></b></span>
```
[LibraryClasses.common]
  <LibraryClassName>|<LibraryInstancePathToInf/Name.inf>

  DebugLib|MdePkg/Library/BaseDebugLibNull/BaseDebugLibNull.inf

```

@snap[west span-20]
@box[bg-royal text-white rounded fragment ](<span style="font-size:01.20em" ><b>Name</b></span>)
@snapend

@snap[west span-25 fragment]
<p align="right"><span style="font-size:02.50em" >@color[yellow](<b>&vert;</b>)</span></p>
@snapend

@snap[midpoint span-40 fragment]
@box[bg-purple-pp text-white rounded  ](<span style="font-size:01.20em" ><b>Implementation<sup>1</sup></b></span>)
@snapend

@snap[midpoint span-40 fragment]
@box[bg-green2 text-white rounded  ](<span style="font-size:01.20em" ><b>Implementation<sup>2</sup></b></span>)
@snapend

@snap[midpoint span-40 fragment]
@box[bg-brick text-white rounded  ](<span style="font-size:01.20em" ><b>Implementation<sup>3</sup></b></span>)
@snapend


@snap[south span-80 ]
@box[bg-green text-white rounded fragment ](<span style="font-size:01.20em" ><b>Consistent set of interfaces</b></span>)
<br>
<br>
<br>
@snapend

@snap[south span-100 ]
@box[bg-purple-pp text-white rounded fragment ](<span style="font-size:01.20em" ><b>Does not describe implementation of the interfaces</b></span>)
@snapend



Note:

#### Syntax for the .dsc file when mapping Libraries to modules

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


---
@title[NULL Library Class]
<p align="right"><span class="gold" ><b>"NULL" Library Class</b></span></p>
<br>
<br>
<br>
<br>
<span style="font-size:0.85em">@color[yellow](<b>Syntax:</b>)</span>
```xml
    Pkg/MyModule/MyModule.inf {
    	 <LibraryClasses>
      	NULL|Pkg/Library/LibName/LibName.inf
      	NULL|Pkg/Library/LibName2/LibName2.inf
  	}


```
<span style="font-size:0.85em">@color[yellow](<b>UEFI Shell example:</b>)</span>
```xml
    ShellPkg/Application/Shell/Shell.inf {
     <LibraryClasses>
       NULL|ShellPkg/Library/UefiShellDriver1CommandsLib/UefiShellDriver1CommandsLib.inf
       NULL|ShellPkg/Library/UefiShellNetwork1CommandsLib/UefiShellNetwork1CommandsLib.inf
	  . . .
    }      

```
@snap[north-west span-40]
<br>
<br>
<br>
@box[bg-royal text-white rounded fragment ](<span style="font-size:01.20em" ><b>Constructors</b></span>)
@snapend

@snap[north-east span-40]
<br>
<br>
<br>
@box[bg-lt-orange text-white rounded fragment ](<span style="font-size:01.20em" ><b>Special Cases</b></span>)
@snapend


@snap[north span-65]
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-navy text-white rounded fragment ](<span style="font-size:0.90em" ><b>NOT &nbsp; "<font face="Consolas">...LibNull</font>" &nbsp; instance</b></span>)
@snapend

@snap[south-east span-40]
@box[bg-purple-pp text-white rounded my-box-pad fragment ](<p style="line-height:80%" ><span style="font-size:0.80em" ><b>Open Source Example</b><br></span><span style="font-size:0.50em" >DxeCrc32GuidedSectionExtractLib <br>ShellPkg as used with Profiles<br>&nbsp; </span></p>)
<br>
@snapend

Note:
- Not a named library
- Not related to LibNull instances (DebugLibNull)
- May not produce any interfaces
- Does all work in constructors
- Can be linked more than once
- Used for special cases
- DXE Core and DXE IPL section file interpreters
- ShellPkg uses the NULL named library with its profiles, thus when compiling a version of the UEFI Shell application, all that is needed is to include the interface as shown in the example on this slide.




---
@title[Locating library classes]
<p align="right"><span class="gold" ><b>Locating Library Classes</b></span></p>

@snap[north-west span-100]
<br>
<br>
@box[bg-royal text-white rounded  my-box-pad fragment](<p style="line-height:80%" align="left"><span style="font-size:01.0em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b>Library based upon</b><br></span><span style="font-size:0.70em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1. Industry specifications &lpar;UEFI, PCI, USB, etc.&rpar; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@color[yellow](<font face="Consolas">MdePkg/MdeModulePkg</font>)<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. Intel’s framework<sup>1</sup> specs <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@color[yellow](<font face="Consolas">IntelFrameworkPkg/IntelFrameworkModulePkg</font>)<br>&nbsp;</p>)
@box[bg-brick text-white rounded  my-box-pad fragment](<span style="font-size:0.90em" >Use the package help files &lpar;<font face="Consolas">.CHM</font>&rpar; to find a library or function<br> <i>Example:</i> <font face="Consolas">MdePkg.chm</font></span>)
<br>
@box[bg-green text-white rounded  fragment](<span style="font-size:0.90em" > Search WorkSpace &lpar;<font face="Consolas">.INF</font>&rpar;  "<font face="Consolas">LIBRARY_CLASS</font>" </span>)
@snapend

@snap[south-west span-50]
<span style="font-size:0.50em" ><sup>1</sup>Intel<sup>&reg;</sup> Platform Innovation Framework for UEFI</span>
@snapend


Note:

How do you find library classes?<br>
The simple answer is ”you have to know what the library class is based on.”
- For example, if it is based on industry standards like the UEFI, PI, SMBIOS, ACPI, etc…you are probably going to find it in the MDE package or maybe in the MDE module package. 





---?image=/assets/images/slides/Slide11_1.JPG
@title[Library Instance Hierarch]
<p align="right"><span class="gold" ><b>Library Instance Hierarchy</b></span></p>

@snap[north-west span-30]
<br>
<br>
<p style="line-height:80%" align="left"><span style="font-size:01.50em" >@color[yellow](<b>Form</b>)</span><br>
<span style="font-size:0.90em" >a hierarchy similar to UEFI drivers</span></p>
@snapend

@snap[north-east span-30]
<br>
<br>
<p style="line-height:80%" align="right"><span style="font-size:01.50em" >@color[yellow](<b>Link</b>)</span><br>
<span style="font-size:0.90em" >your module to another</span></p>
@snapend

@snap[north span-100]
<br>
<br>
<br>
<br>
@css[text-white fragment](<p style="line-height:80%" align="center"><span style="font-size:0.80em" ><font face="Consolas">DebugLib</font></span></p>)
@css[text-white fragment](<p style="line-height:80%" align="center"><span style="font-size:0.70em" ><font face="Consolas">DebugLibSerialPort</font><br> &lpar;Instance&rpar;</span></p>)
@css[text-white fragment](<p style="line-height:80%" align="center"><span style="font-size:0.80em" ><br>SerialPort &lpar;Class&rpar;</span></p>)
@css[text-white fragment](<p style="line-height:80%" align="center"><span style="font-size:01.0em" ><br><font face="Consolas">MdePkg</font> &lpar;Specs&rpar;</span></p>)
@css[text-white fragment](<p style="line-height:80%" align="center"><span style="font-size:0.70em" ><br><br>@color[red](<b>Build error</b>):Instance of Library class &lbrack;<font face="Consolas">Foo...Lib</font>&rbrack; is not found... <br>Consumed by module &lbrack;<i>My Module.inf</i>&rbrack;</span></p>)

@snapend


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




---
@title[Commonly Used Base Library Classes]
<p align="right"><span class="gold" ><b>Commonly Used Base Library Classes</b></span></p>

@snap[north-west span-100 fragment]
<br>
<br>
<p style="line-height:90%" align="left"><span style="font-size:0.80em; font-family: Consolas; font-weight: bold;" >BaseLib &nbsp;&nbsp;DebugLib <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UefiLib<br>
&nbsp;UefiApplicationEntryPoint</span></p>
@snapend


@snap[north-east span-100 fragment]
<br>
<br>
<p style="line-height:90%" align="right"><span style="font-size:0.80em; font-family: Consolas; color: #00b0f0; font-weight: bold;" >
@color[yellow](UefiDriverEntryPoint)
<br>UefiBootServicesTableLib&nbsp;&nbsp;
<br> @color[yellow](DxeCoreEntryPoint)&nbsp;&nbsp; 
<br>DevicePathLib&nbsp;&nbsp;IoLib
<br> &nbsp;&nbsp;PrintLib&nbsp;&nbsp;@color[yellow](PeimEntryPoint)
<br>&nbsp;UefiScsiLib @color[#87E2A9](BaseMemoryLib)</span></p>
@snapend

@snap[north-west span-100 fragment]
<br>
<br>
<p style="line-height:90%" align="left"><span style="font-size:0.80em; font-family: Consolas; color: #FFC000; font-weight: bold;" ><br><br><br>
CpuLib&nbsp;&nbsp;UefiUsbLib&nbsp;PciLib<br>
@color[#87E2A9](MemoryAllocationLib)<br>
&nbsp;@color[yellow](PeiCoreEntryPoint)<br>
&nbsp; &nbsp;UefiRuntimeLib &nbsp; &nbsp;&nbsp;@color[#87E2A9](SmmMemLib)</span></p>
@snapend


@snap[north-west span-100 fragment]
<br>
<br>
<p style="line-height:90%" align="left"><span style="font-size:0.80em; font-family: Consolas; color: #FFC000; font-weight: bold;" ><br><br><br><br><br><br><br>
&nbsp;@color[#00b0f0](DxeSerivesLib)&nbsp;&nbsp;&nbsp;@color[yellow](SynchronizationLib)&nbsp;PciExpressLib<br>
DxePcdLib&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@color[#00b0f0](UefiRuntimeServicesTableLib) <br>
&nbsp; &nbsp;PciSegmentLibLib &nbsp;@color[yellow](PeiServicesLib)<br>
&nbsp; PeiPcdLib&nbsp;&nbsp;DxeHobLib &nbsp;&nbsp;@color[#87E2A9](UefiFileHandleLib)</span></p>
@snapend

@snap[south span-90]
@box[bg-purple-pp text-white rounded my-box-pad fragment ](<p style="line-height:80%" ><span style="font-size:0.90em" ><b>@color[yellow](MANY!!!) &nbsp;&nbsp;Many Libraries in the EDK II code</b><br>&nbsp; </span></p>)
@snapend

Note:
Key point is that this soon becomes an Eye chart of many - MANY Many Libraries in the EDK II code

---?image=/assets/images/slides/Slide48.JPG
@title[MdePkg Library Doc. Location ]
<p align="right"><span class="gold" ><b>MdePkg Library .CHM file Location</b> </span></p>
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
<p align="right"><span class="gold" ><b>Library Navigation Demonstration</b></span></p>

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
<p align="right"><span class="gold" ><b>Library Navigation Demonstration</b></span></p>
![video](https://www.youtube.com/embed/s8Zw1w1iQS4)
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
<p align="right"><span class="gold" ><b>Defining a UEFI Application</b></span></p>
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
<p align="right"><span class="gold" ><b>Defining a UEFI Application</b></span></p>
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
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>


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
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>


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
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>


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
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>


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
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>


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
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide66.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 02]
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide67.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 03]
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide68.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 04]
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide69.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 05]
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over


+++?image=/assets/images/slides/Slide70.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Executing OS Load App 06]
<p align="right"><span class="gold" ><b>Executing Applications</b></span></p>

Note:

Same as the UEFI application except will not return to the UEFI Loader and the OS will take over



---
<!-- .slide: data-transition="none" -->
@title[Driver vs. Application]
<p align="right"><span class="gold" ><b>Driver Vs. Application</b></span></p>

<table id="recTable">
	<tr>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b></b></span></p></td>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Driver</b></span></p></td>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Application</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Loaded by: </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >UEFI Loader </span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >UEFI Loader </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Interface available: </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >All</span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >All </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Consume protocols? </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >YES</span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >YES </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Produce protocols? </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: #F2f2f2" >YES</span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: #F2f2f2" >NO </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Typically Driven by? </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: #F2f2f2" >System</span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: #F2f2f2" >User </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Typically use? </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: #F2f2f2" >Support Hardware</span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: #F2f2f2" >Any </span></p></td>
	</tr>
</table>




+++
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Driver vs. Application]
<p align="right"><span class="gold" ><b>Driver Vs. Application</b></span></p>

<table id="recTable">
	<tr>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b></b></span></p></td>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Driver</b></span></p></td>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Application</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Loaded by: </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >UEFI Loader </span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >UEFI Loader </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Interface available: </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >All</span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >All </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Consume protocols? </b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >YES</span></p></td>
		<td  bgcolor="#F2f2f2" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >YES </span></p></td>
	</tr>
	<tr class="fragment">
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Produce protocols? </b></span></p></td>
		<td  bgcolor="#75deFF" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >YES</span></p></td>
		<td  bgcolor="#FFF5db" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >NO </span></p></td>
	</tr>
	<tr class="fragment">
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Typically Driven by? </b></span></p></td>
		<td  bgcolor="#75deFF" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >System</span></p></td>
		<td  bgcolor="#FFF5db" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >User </span></p></td>
	</tr>
	<tr class="fragment">
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b>Typically use? </b></span></p></td>
		<td  bgcolor="#75deFF" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >Support Hardware</span></p></td>
		<td  bgcolor="#FFF5db" height=".025"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >Any </span></p></td>
	</tr>
</table>

Note:



---?image=assets/images/binary-strings-black2.jpg
@title[Writing EDK II Applications Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;EDK II UEFI Applications </span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;How to Write a EDK II UEFI Application</span>


---
@title[Application Files Placement]
<p align="right"><span class="gold" ><b>Application Files Placement</b></span></p>

@css[text-white fragment](@fa[certificate gp-bullet-ltgreen]<span style="font-size:0.8em" >&nbsp;&nbsp;Application source code can go anywhere in the EDK II <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;workspace including PACKAGES_PATH</span> )

@css[text-white fragment](@fa[certificate gp-bullet-cyan]<span style="font-size:0.8em" >&nbsp;&nbsp;All code and include files go under a single directory containing<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; an INF</span> )

@css[text-white fragment](@fa[certificate gp-bullet-yellow]<span style="font-size:0.8em" >&nbsp;&nbsp;EDK  II Sample Applications can be found here:</span><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-size:0.7em; background-color: #080808">&nbsp;&nbsp;<font face="Consolas">  edk2/MdeModulePkg/Application   </font>&nbsp;&nbsp;</span>)

@css[text-white fragment](@fa[certificate gp-bullet-gold]<span style="font-size:0.8em" >&nbsp;&nbsp;Typically, modules reside within a package:</span> )

@box[bg-grey-05 text-white rounded  my-box-pad fragment](<p style="line-height:60%" align="left"><span style="font-size:0.7em; font-family: Consolas" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  /MyWorkSpace      &nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    /edk2/MyPkg          &nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;       /Application &nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;         /MyApp     &nbsp;&nbsp;<br>&nbsp;</span></p>)

@snap[south-east span-55 fragment]
![MyAppdir](/assets/images/MyAppDir.png)
<br>
@snapend

Note:

Same as slide

---?image=/assets/images/slides/Slide35_1.JPG
@title[Module .INF File]
<p align="right"><span class="gold" ><b>Module .INF File</b></span></p><br>
<span style="font-size:01.1em" ><font color="yellow">Syntax</font></span>
<div class="left1">
<br>
<br>
<br>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/blob/master/MdeModulePkg/Application/VariableInfo/VariableInfo.inf">INF text file example </a></span>
</div>
<div class="right1">
   <p style="line-height:60%" ><span style="font-size:0.65em; font-family: Consolas">&nbsp; &nbsp;  INFfile ::= [&lt;Header&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &lt;Defines&gt;<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;BuildOptions&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Sources&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Binaries&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Guids&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Protocols&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Ppis&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Packages&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;LibraryClasses&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Pcds&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;UserExtensions&gt;]<br>
   &nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp; [&lt;Depex&gt;]<br>
   </span></p>
</div>


Note:

Update to define all Sources (.c, .h, .uni) , libraries, Packages, Guids,  PCDs be used by the Module

See EDK II INF  File Specification for more details and examples

1 Depex only used with specific Module types






---
@title[Application INF Files -DEFINES]
<p align="right"><span class="gold" ><b>Application INF Files <font face="Consolas">[DEFINES]</font><b></span></p>



<table id="recTable">
	<tr>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Field</b></span></p></td>
		<td align="center" bgcolor="#0070C0" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Description</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">INF_VERSION</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >1.25* - Version of the INF spec. </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">BASE_NAME</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >What’s the name of the application </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">FILE_GUID</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >Create a GUID for your module </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">MODULE_UNI_FILE</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >Meta-data - localization for Description, Abstract</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">VERSION_STRING</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" > Version number</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">ENTRY_POINT</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" > Name of the entry function to call </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">MODULE_TYPE</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" > UEFI_APPLICATION</span></p></td>
	</tr>
</table>



@snap[south-west span-100]
<span style="font-size:0.5em" ><font color="yellow">*EDK II Specifications: </font> <a href="https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications">https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications </a></span>
@snapend


Note:

- There are other optional fields
- Check the Extended INF Specification

#### defines
- INF_VERSION 1.25* - Version of the INF spec.
- BASE_NAME What’s the name of the application
- FILE_GUID Create a GUID for your module guidgen.com
- MODULE_UNI_FILE Meta-data - localization for Description & Abstract
- VERSION_STRING Version number
- ENTRY_POINT Name of the function to call ie MyMainEntryPoint();
- MODULE_TYPE UEFI_APPLICATION

---
<!-- .slide: data-background-transition="none" -->
@title[Sample INF file]
<p align="right"><span class="gold" ><b>Sample INF file</b></span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  MODULE_UNI_FILE                = MyFile.uni
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
<p align="right"><span class="gold" ><b>Sample INF file</b></span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  MODULE_UNI_FILE                = MyFile.uni
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

@[1-8](Defines for this .INF file; BASE_NAME results in this name.efi file)
@[4-4](OPTIONAL: UNI Text file for localization of descriptions and abstract  MyFile.uni)
@[5-5](Always get a new quid .i.e http://guidgen.com)
@[7-7](User defined string syntax is <font face="Consolas">number</font> dot <font face="Consolas">number</font>)
@[8-8](The main entry point of the module in one of the .c files in list of sources)
@[10-11]( Source: .c, .h, .uni, .vfr, any files needed for the compiler/linker/lib etc)
@[13-17](Package dependencies and Libraries this module will include in its final binary image)

Note:

-  INF_VERSION            see spec
-  BASE_NAME            BASE_NAME results in this name.efi file
-  MODULE_UNI_FILE     OPTIONAL: UNI Text file for localization of descriptions and abstract MyFile.uni
-  FILE_GUID           Always get a new quid
-  MODULE_TYPE         UEFI_APPLICATION or driver or PEIM or DXE
-  VERSION_STRING       User defined string number dot number
-  ENTRY_POINT         The main entry point of the module in one of the .c files in list of sources


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
<p align="right"><span class="gold" ><b>Sample Application "C" File</b></span></p>
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
<p align="right"><span class="gold" ><b>Sample Application "C" File</b></span></p>
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
<p align="right"><span class="gold" ><b>UEFI Application Vs. EADK Application</b></span></p>
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
<p align="right"><span class="gold" ><b>Sample INF file using EDK II EADK</b></span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  MODULE_UNI_FILE                = MyFile.uni
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
<p align="right"><span class="gold" ><b>Sample INF file using EDK II EADK</b></span></p>

```XML
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = MyApplication
  MODULE_UNI_FILE                = MyFile.uni
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
@[8]( Entry point is a library in the shell to get parameters from the command line)
@[13-15]( Packages included for standard "C" lib and Shell Lib)
@[18-21]( Library classes for ANSI "C" and Standard IO "stdio.h")

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
<p align="right"><span class="gold" ><b>Sample "C" file using EDK II EADK</b></span></p>
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
  



---
@title[Driver File Placement]
<p align="right"><span class="gold" ><b>Driver File Placement</b></span></p>

@css[text-white fragment](@fa[certificate gp-bullet-ltgreen]<span style="font-size:0.8em" >&nbsp;&nbsp;Driver source code can go anywhere in the EDK II <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;workspace </span> )

@css[text-white fragment](@fa[certificate gp-bullet-cyan]<span style="font-size:0.8em" >&nbsp;&nbsp;All code and include files go under a single directory containing<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; an INF</span> )

@css[text-white fragment](@fa[certificate gp-bullet-yellow]<span style="font-size:0.8em" >&nbsp;&nbsp;Good example of UEFI Drivers can be found here:</span><br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-size:0.7em; background-color: #080808">&nbsp;&nbsp;<font face="Consolas">  /MdeModulePkg/Bus/ScsiDiskDxe   </font>&nbsp;&nbsp;</span>)

@css[text-white fragment](@fa[certificate gp-bullet-gold]<span style="font-size:0.8em" >&nbsp;&nbsp;Typically, Driver modules reside within a package:</span> )

@box[bg-grey-05 text-white rounded  my-box-pad fragment](<p style="line-height:60%" align="left"><span style="font-size:0.7em; font-family: Consolas" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  /MyWorkSpace      &nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;    /edk2/MyPkg          &nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; /Include &nbsp;&nbsp;<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; /MyDriver     &nbsp;&nbsp;<br>&nbsp;</span></p>)


@snap[south-east span-55 fragment]
<br>
![MyDriverdir](/assets/images/MyDriverDir.png)
<br>

Note:
Same as slide


---
<p align="right"><span class="gold" ><b>Driver INF Files: <font face="Consolas">[DEFINES]</font></b></span></p>





<table id="recTable">
	<tr>
		<td align="center" bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Field</b></span></p></td>
		<td align="center" bgcolor="#0070C0" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.9em" ><b>Description</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">INF_VERSION</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >1.25* - Version of the INF spec. </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">BASE_NAME</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >What’s the name of the driver </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">FILE_GUID</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >Create a GUID for your module </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">MODULE_UNI_FILE</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" >Meta-data - localization for Description, Abstract</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">VERSION_STRING</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" > Version number</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">ENTRY_POINT</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" > Name of the entry function to call </span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#0070C0" height=".025"><p style="line-height:010%"><span style="font-size:0.65em" ><b><font face="Consolas">MODULE_TYPE</font></b></span></p></td>
		<td  bgcolor="#F2f2f2" height=".025" width="70%"><p style="line-height:010%"><span style="font-size:0.7em; color: black" > <font face="Consolas">UEFI_DRIVER, DXE_DRIVER, PEIM,</font> etc...</span></p></td>
	</tr>
</table>



@snap[south-west span-100]
<span style="font-size:0.5em" ><font color="yellow">*EDK II Specifications: </font> <a href="https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications">https://github.com/tianocore/tianocore.github.io/wiki/EDK-II-Specifications </a></span>
@snapend



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




---?image=/assets/images/slides/Slide47_1.JPG
@title[Changes for a UEFI Driver Module]
<p align="right"><span class="gold" ><b>Changes for a UEFI Driver Module</b></span></p>

@css[text-white fragment](<span style="font-size:0.9em" >Applications can be converted to a driver</span> )
<br>
<br>
@css[text-white fragment](<span style="font-size:0.9em" >@color[yellow](But) . . . It remains in memory after it runs</span> )
@snap[north-east span-15 fragment]
<br>
<br>
![uefi_logo](/assets/images/uefi_logo.png)
@snapend
<br>
@css[text-white fragment](<p style="line-height:80%" ><span style="font-size:0.9em" >UEFI Driver Module requirements:<br>&nbsp;&nbsp;&bull;&nbsp;&nbsp;Driver Binding Protocol<br>&nbsp;&nbsp;&bull;&nbsp;&nbsp;Component Name2 Protocol &lpar;recommended&rpar;</span> </p>)

<br>
@css[text-white fragment](<span style="font-size:0.9em" >DXE/PEIM/other Driver requirements</span> )


Note:

An Application can be converted to  UEFI Drier by simply changing the MODULE_TYPE to UEFI_DRIVER

(But) . . . It remains in memory after it runs
 
It is better to also add the UEFI Driver Binding Protocol and / or Component Name Protocol (others maybe needed for whatever the job is for the driver that is being created)

Other requirements maybe on DXE and/or PEIM and/or other types of UEFI Drivers 
i.e. a serial UEFI driver may require the Serial IO  protocol

---
<!-- .slide: data-transition="none" -->
@title[Sample INF Driver file]
<p align="right"><span class="gold" ><b>Sample Driver INF file</b></span></p>

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


---?image=/assets/images/slides/Slide49_1.JPG
@title[INF Usage fields – DIST files ]
<p align="right"><span class="gold" ><b>INF Usage fields – DIST files</b> </span></p>

<span style="font-size:01.25em" >@color[yellow](<i><b>Optional</b></i>) </span>&nbsp;&nbsp;&nbsp;<b>UEFI Spec - Package Distribution<b>
<div class="left1">
<p style="line-height:80%"><span style="font-size:0.8em" >Usage field used by the Build tools for creating the .Dist file for binary modules</span></p>
     <ul style="list-style-type:none; line-height:0.7;">
        <li><span style="font-size:0.7em" >[GUID]</span></li>
        <li><span style="font-size:0.7em" >[PCD]</span></li>
        <li><span style="font-size:0.7em" >[PROTOCOL]</span></li>
		<li><span style="font-size:0.7em" >[PPIS]</span></li>
     </ul>
<p style="line-height:80%"><span style="font-size:0.6em" >1 Usage Block&nbsp;&nbsp;  - "&num;&num;" After the entry<br><i>n</i>&nbsp;Usage Blocks - "&num;&num;" Precede the entry	</span></p>
</div>
<div class="right1">
<br>
<br>
<p style="line-height:80%"><span style="font-size:0.7em" > @color[yellow](<b>&nbsp;&nbsp;Usage Key Word</b>)</span></p>
    <ul style="list-style-type:none; line-height:0.7;">
        <li><span style="font-size:0.45em" >&num;&num; UNDEFINED</span></li>
        <li><span style="font-size:0.45em" >&num;&num; CONSUMES</span></li>
        <li><span style="font-size:0.45em" >&num;&num; SOMETIMES_CONSUMES</span></li>
		<li><span style="font-size:0.45em" >&num;&num; PRODUCES</span></li>
		<li><span style="font-size:0.45em" >&num;&num; SOMETIMES_PRODUCES</span></li>
		<li><span style="font-size:0.45em" >&num;&num; TO_START</span></li>
		<li><span style="font-size:0.45em" >&num;&num; BY_START</span></li>
 		<li><span style="font-size:0.45em" >&num;&num; NOTIFY</span></li>
    </ul>
  
</div>
@snap[south-east span-40]

<p align="right" style="line-height:20%"><span style="font-size:02.25em" >@color[yellow](&rbrace;) </span><span style="font-size:0.5em" >UEFI Protocol&nbsp;&nbsp;<br><br><br><br><br><br><br>&nbsp;</span></p>
<br>
@snapend

Note:


Usage field used by the Build tools for creating the .Dist file for binary modules 
can be used in applications that parse the .DIST files.
- Example:  PCDs of type "Patch-able"

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
<p align="right"><span class="gold" ><b>INF File Usage Block examples</b></span></p>
<br>


```xml

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


@[1-8](The Usage Block text comes before the <font face="Consolas">gEfiGlobalVariableGuid</font> GUID)
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
<p align="right"><span class="gold" ><b>INF File Usage Block examples</b></span></p>
<br>

```xml

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


@[3-5](The Usage Block text comes before the <font face="Consolas">gEfiDevicePathProtocolGuid</font> protocol GUID)
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
<p align="right"><span class="gold" ><b>UEFI Driver Example - Disk I/O</b></span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a></span><br>

Note:
- PCI Platform DXE
- Under workspace directory
- Under the Platform Package

---
@title[UEFI Driver Example - Disk I/O]
<p align="right"><span class="gold" ><b>UEFI Driver Example - Disk I/O</b></span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a>- entry point</span><br>

@snap[north-west span-50 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="cyan">"C" file</font></span></p>

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

@snapend


@snap[north-east span-48 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="yellow">INF file</font></span></p>

```
[Defines]
 . . .
  ENTRY_POINT  = InitializeDiskIo
```

@snapend


Note:



---
@title[UEFI Driver Example - Disk I/O 02]
<p align="right"><span class="gold" ><b>UEFI Driver Example - Disk I/O</b></span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a>- Supported </span><br>

@snap[north-west span-50 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="cyan">"C" file</font></span></p>

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

@[3](Entry point for Supported)
@[11]( Using the global gEfiBlockIoProtocolGuid protocol to determine if this device controller handle is a Block I/O device)

@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="yellow">INF file</font></span></p>

```
[Protocols]
  . . .
  gEfiBlockIoProtocolGuid  ## TO_START
```

@snapend

Note:

Using the global gEfiBlockIoProtocolGuid protocol to determine if this device controller handle is a Block I/O device

---
@title[UEFI Driver Example - Disk I/O 03]
<p align="right"><span class="gold" ><b>UEFI Driver Example - Disk I/O</b></span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Universal/Disk/DiskIoDxe ">https://github.com/tianocore/edk2 /Disk/DiskIoDxe  </a>- Start</span><br>

@snap[north-west span-50 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="cyan">"C" file</font></span></p>

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

@[3](Entry point for Start function)
@[13-14]( Using the global gEfiDiskIoProtocolGuid and gEfiDiskIo2ProtocolGuid protocols to INSTALL handles to)
@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="yellow">INF file</font></span></p>

```
[Protocols]
  . . .
  gEfiDiskIoProtocolGuid   ## BY_START
  gEfiDiskIo2ProtocolGuid  ## BY_START

```

@snapend

Note:



---?image=/assets/images/slides/Slide117_1.JPG
@title[DXE Driver Example - PlatformInfoDxe]
<p align="right"><span class="gold" ><b>DXE Driver Example - PlatformInfoDxe</b></span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2-platforms/tree/devel-MinnowBoardMax-UDK2017/Vlv2TbltDevicePkg/PlatformInfoDxe">https://github.com/tianocore/edk2-platforms/ PlatformInfoDxe</a></span><br>

Note:
- PCI Platform DXE
- Under workspace directory
- Under the Platform Package



---
@title[DXE Example .INF File - PlatformInfoDxe]
<p align="right"><span class="gold" ><b>DXE Driver Example - PlatformInfoDxe</b></span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2-platforms/tree/devel-MinnowBoardMax-UDK2017/Vlv2TbltDevicePkg/PlatformInfoDxe">https://github.com/tianocore/edk2-platforms/ PlatformInfoDxe</a></span><br>

@snap[north-west span-50 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="cyan">"C" file</font></span></p>

```
#include “PlatformInfoDxe.h“
// • • •
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
@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="yellow">INF file</font></span></p>

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
@snapend

@snap[south-west span-100 ]
<span style="font-size:0.6em"  >Notice the MODULE TYPE, C function Entry point and the [Depex] differences in the INF file </span>
<br>
<br>
<br>
@snapend

Note:

MODULE_TYPE         = DXE_DRIVER

Depex section is part of the Dxe driver INF file

---?image=/assets/images/slides/Slide121_1.JPG
@title[PEI Driver (PEIM) Example - CpuIoPei]
<p align="right"><span class="gold" ><b>PEI Driver (PEIM) Example - CpuIoPei</b></span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/UefiCpuPkg/CpuIoPei">https://github.com/tianocore/edk2/ UefiCpuPkg/CpuIoPei  </a> </span>

Note:
- PCI Platform DXE
- Under workspace directory
- Under the Platform Package


---
@title[PEI Driver (PEIM) Example - CpuIoPei]
<p align="right"><span class="gold" ><b>PEI Driver (PEIM) Example - CpuIoPei</b></span></p>
@fa[github gp-bullet-gold]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/UefiCpuPkg/CpuIoPei">https://github.com/tianocore/edk2/ UefiCpuPkg/CpuIoPei  </a> </span>
@snap[north-west span-50 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="cyan">"C" file</font></span></p>

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

@[5](Entry point for this Dxe Driver)
@[6-7]("FileHandle" - Instead of the ImageHandle & NO EFI_SYSTEM_TABLE - Not yet defined)

@snapend

@snap[north-east span-48 ]
<br>
<br>
<br>
<p style="line-height:45%" align="left" ><span style="font-size:0.8em" ><font color="yellow">INF file</font></span></p>
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
@snapend

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

Copyright (c) 2020, Intel Corporation. All rights reserved.
**/

```
