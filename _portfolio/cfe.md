---
layout: post
title: Creole Forth for Excel
feature-img: "img/sample_feature_img.png"
thumbnail-path: "img/cfe_excel.png"
short-description: Creole Forth for Excel is a simple scripting language that runs on top of Excel spreadsheets.

---

<strong>Summary</strong>

The tasks and requirements in the corporate workplace can change at a moment's notice. They often are subject to severe time constraints, need to be simplified and automated to be done in a timely and accurate manner, or to be delegated to colleagues. Scripting languages such as VBA, Tcl/Tk or Python work but sometimes I want something even simpler where pre-existing code can be easily glued togehter. Creole Forth for Excel is a custom scripting language written on top of Excel VBA and it offers "something extra" in this niche. 

<strong>Explanation</strong>

I have worked in software development and support in a number of different companies. Repetitive,  complex processes that are poorly and/or loosely defined are a common occurrence. They were often done by colleagues manually, poorly, or sometimes not at all. I often was required to run them, document them myself, and then pass them on to other people in a limited amount of time, so I built a tool to help accomplish this requirement more easily. 

In his essay <a href="https://www.tcl.tk/doc/scripting.html">Scripting: Higher Level Programmingfor the 21st Century</a> John Ousterhout makes a distinction between scripting languages such as Tcl and Perl and systen languages such as C. Scripting languages offer advantages in rapid prototyping, ease of development, and putting together software from pre-existing components. System languages require slower development, but can offer advantages in performance, conservative usage of resources, and be used to create functionality that can be exploited by a scripting language that would otherwise not be available. 

<strong>Problem</strong> 

What kind of scripting language is especially useful in workplace automation? Below are some suggestions:

<ol>
<li>Runs on top of a universally or near universally available environment.</li>
<li>Open source and can be widely shared.</li>
<li>Simple to understand. </li>
<li>Easily extensible.</li>
<li>Can easily be integrated with pre-existing processes and code.</li>
<li>Easily integrated with the environment it was built in, including debugging facilities and component libraries.</li> 
<li>Can be deployed with few or no dependencies.</li> 
</ol>

<strong>Solution</strong>

Creole Forth for Excel (CFE) addresses all of the issues defined in the Problems section.

<ol>
<li>
Universal environment. Excel, along with the rest of the Microsoft Office suite, is ubiquitous in the corporate environment. 
</li><br />

<li>
Open source. CFE is available on Github and can be used simply by downloading the spreadsheet from a repository. No setup
work is required beyond enabling macros. 
</li><br />

<li>
Simplicity. Most programming languages are complex to parse and require symbol tables and complex lookahead. The
RPN syntax of CFE requires no symbol tables and is trivial to parse. Parameter passing is done via stacks.
</li><br />

<li>
Ease of extensibility. Extensions can either be done by introducing new "primitives" written as VBA code, or through compiled
high-level definitions.
</li><br />

<li>
CFE can easily call external modules written in another language. Even though it lives on Windows, it can also be configured to
execute code remotely (such as on Unix systems) through a variety of mechanisms. 
</li><br />

<li>
Easy integration. Since CFE is a macro language built directly on top of Excel VBA, it has all the power available to the VBA
environment, despite being a much simpler language. The VBA debugging tools, form and component editors, libraries, and scriptable
COM objects are all readily available to it. 
</li><br />

<li>
Easy deployment. Deployment is as simple as moving a spreadsheet out to a network folder. Even configuration files such as ini
files are not required since that information can just as easily be stored in a spreadsheet tab. 
</li><br />
</ol>


<strong>Results</strong> 

Since CFE was developed in August of 2016, it has been the basis of numerous successful projects. Below are 
some examples:

<ol>
<li>
ETL helper application. Different loading task sets are organized in a tabbed dialog box. The main task set is for a complex
monthly loading process which had to be initiated with a combination of Linux scripts and Oracle record inserts. It also handles
the annual scheduling and scripted the email replies. 
</li><br />

<li>
Master issues log tracker. Centralizes and tracks different database tables that are being tested, their field names, and their
issues. Storage of links to intranet web sites and network resources can be added by a simple point and click. 
</li><br />

<li>
SAS code generator. This application generates code to compare two equivalent tables in different databases based on a "crosswalk"
in the form of a spreadsheet. The resulting code can then be run with the SAS system. 
</li><br />

<li>
Supermemo export/import integration utility. Spaced repetition systems such as Anymemo (available on the Android) allow the import
of material from Supermemo via xml files, but do not support import back into Supermemo. This utility addresses that shortcoming and 
allows the user to combine the advantages of both systems.  
</li><br />
</ol>

<strong>Conclusion</strong>

CFE has offered both value and convenience in automating and simplifying complex, ill-defined tasks where there are time
and resource constraints, along with some pre-existing tools that could be integrated with it. It could also be used in more conventional 
"shrink-wrapped" projects, although that's not its primary hiche.

<strong>Additional information (right-click to download)</strong>

<a href="https://github.com/tiluser/Creole-Forth-For-Excel/blob/master/Creole%20forth%20for%20excel%20-%20Forth%20Day.pptx">Powerpoint for Creole Forth for Excel</a>

<a href="https://github.com/tiluser/Creole-Forth-For-Excel/blob/master/How%20to%20build%20a%20primitive%20in%20CFE.pptx">Powerpoint tutorial on building CFE primitives</a>