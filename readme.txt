Ophis conversion of geoProgrammer sample files
==============================================

Conversions of the geoProgrammer sample application source file to the Ophis
assembler.

Converted by Daniel England, 2016.

Released to the Public Domain.


Introduction
------------

GEOS is an operating system that is run on a C64, C128 or Apple IIe.  It is a
GUI OS which was quite remarkable at the time given the constraints of its
target systems.

There were several assemblers available for GEOS, notably one from the 
developers of GEOS themselves - Berkeley Softworks - called geoAssember.  It 
was a fully featured assembler and even produced relocatable object files.  It 
was packaged with a linker and debugger in a package called geoProgrammer.

geoProgrammer came with samples for three different application types.  One for
an application with a sequential structure, one for an application with a VLIR
structure and another for a Desk Accessory.  These samples have been translated
for use with the Ophis assembler.


Compiling
---------

Use Ophis to produce the required, constituent binary files.  GEOS files are
constructed from a number of data forks.  The binary files are for each of these
forks.  To create a finished application file, you will need a tool such as the
one I wrote (GEOSBuild) to assemble the files on a disk image.

You can get Ophis from the following address:

	<https://michaelcmartin.github.io/Ophis/>

You can get GEOS Build from the following address:

	<https://github.com/m3wP/GEOSBuild>
	

Files
-----

All applications will require the following (non code producing files):

	geosSym.oph
	geosMac.oph


The files for the SampleSeq application are:

	SamSeqHrd.oph
	SamSeq.oph
	SamSeq.gbuild
	

The files for the SampleVlir application are:

	SamVlirHdr.oph
	SamVlirRes.oph
	SamVlirFile.oph
	SamVlirEdit.oph
	SamVlir.gbuild
	
Non code producing files for the SampleVlir application are:

	SamVlirEquates.oph
	SamVlirZPVars.oph
	
The files for the SampleDA Desk Accessory are:

	SamDAHdr.oph
	SamDA.oph
	SamDA.gbuild
	

Notes
-----

There were a number of issues or caveats raised when converting the files.  Most
notably were issues in geosMac.  

Firstly, Ophis does not support conditional blocks so the macro AddVW had to be
changed to two separate macros, AddVW_b and AddVW_w.

Secondly, Ophis does not support the bitwise shift operators and so several 
macros had to be changed to accept bit masks instead of bit indexes.  These may
be difficult to use.

Please see the source files for further details.  I have put my name against any
change of note (dengland).


Contact
-------

I can be contacted for further information regarding these files at the following
address:

        mewpokemon {you know what goes here} hotmail {and here} com

Please include the word "geoProgrammer" in the subject line.



Daniel England.