## Metadata transformation using OpenRefine for VDE norms/standards

Metadata processing is based on the 'save result list' option offered by www.normenbibliothek.de (on the upper left). The csv data obtained from the platform may then be restructured by using one of the provided JSON-scripts in OpenRefine. Use standard (CSV) parsing settings on the import to OpenRefine and create a project with the downloaded data. Finally, paste code to the 'Apply'-prompt, which can be found at 'Undo/Redo' section (on the uper left), perform the transformation and export the results to any considered file format.

At first, the script has been intended to work without enrichment of further metadata by default. However, a additional version is provided here, which appends other desirable items, such as publisher, place of publication and a default DDC-Term. Please note, that basic functionality emerges from the specific design of import and data storage processes at MPDL. The used MAB schema as well as the publishing details in fields 410/412/425a may not be suitable to every library.

#### VDE_csv2mab.json<br>
JSON file used to process provided data only.<br>

#### VDE_csv2mab_plus.json<br>
JSON file for additionally adding publisher, publication place and default DDC.<br>

#### VDE_csv2mab_ALEPHseq.json<br>
JSON file for direct conversion to ALEPH sequential format: To be used if metadata shall be imported to an ALEPH library.
Don't forget to convert exported file to Unix format by:<br>
_dos2unix \<filename\>_<br>
Final character replacements by:<br>
_sed 's/^"//g; /.*370a  L $$a$/d; /.*501   L $$a$/d; /.*540   L $$z$/d; /.*564   L $$a$/d; s/700b  L $$a621"/700b  L $$a621/g' \<filename\>_<br>

#### VDE_csv2mab_ALEPHseq_export.json<br>
JSON file contains pre-defined export settings to be applied at saving OpenRefine Results. Choose "Export" -> "Custom Tabular Exporter" -> "Option Code" where you can paste and apply the settings for an optimized output.
