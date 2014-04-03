FOPDoc
======

Documentation for the Fallout 3 and Fallout: New Vegas plugin file formats. 

The Oblivion, Skyrim, Fallout 3 and Fallout: New Vegas plugin file formats are all very similar, but while there exists good documentation for [Oblivion](http://www.uesp.net/wiki/Tes4Mod:Mod_File_Format) and [Skyrim](http://www.uesp.net/wiki/Tes5Mod:Mod_File_Format), there is no equivalent for Fallout 3 and Fallout: New Vegas. The aim is for this repository to become that equivalent.


### Format & Structure

This documentation is written in [GitHub Flavored Markdown](https://guides.github.com/overviews/mastering-markdown/) and stored in a Git repository on [GitHub](https://github.com/WrinklyNinja/fopdoc) because:

* Revision control is good.
* You can download the documentation for offline reading.
* Markdown gives readable plain text and can also be readily converted to HTML.
* GitHub offers in-browser editing and HTML preview for Markdown.
* GitHub makes it easier to make, share and integrate edits with others.

The structure is as follows:

* Each game's documentation goes in a separate folder in the repository root, eg. the Fallout 3 documentation is stored in the [FO3](FO3) folder.
* Information about common data structures is stored in the game's folder.
* The specifics of a record type get documented in a separate file in `<game>/Records`, named using its 4-character type and with the `.md` file extension. Eg. Fallout 3's [TES4 record documentation](FO3/Records/TES4.md).
* Fields of the `struct` type that are present in multiple records with the same structure and semantics are documented in separate files in `<game>/Records/Fields`. The same can be done for collections of fields that always appear together.

Fallout: New Vegas likely shares many of the same data structures, so to avoid repitition reference should be made back to the FO3 docs and only differences written out in full.


### File Format Data Source

The most complete open-source implementation of plugin parsers for these games is [TES5Edit](https://code.google.com/p/skyrim-plugin-decoding-project/), written in Delphi. The information on the file formats contained within its parsing code will be adapted into a reasonably generic format that programmers should be able to interpret regardless of their preferred language, similar to how it is presented by [UESP.net](http://www.uesp.net/wiki/Tes5Mod:Mod_File_Format).

The FO3 definitions in TES5Edit are found [here](https://skyrim-plugin-decoding-project.googlecode.com/svn/TES5Edit/trunk/Delphi%20XE/wbDefinitionsFO3.pas). [This page](https://code.google.com/p/skyrim-plugin-decoding-project/wiki/DecodingRecords) may be useful in understanding the code. In practice though, searching [this source file](https://skyrim-plugin-decoding-project.googlecode.com/svn/TES5Edit/trunk/Delphi%20XE/wbInterface.pas) may be more useful.


### Contributing

I'm unfamiliar with Delphi / Pascal, so extracting the information is slow work. Anyone who's willing to help out is very welcome to: just fork the repository, and feel free to open issues on its issue tracker if you want to discuss something. You don't even need to leave your web browser, since the files can be edited and previewed on GitHub.
