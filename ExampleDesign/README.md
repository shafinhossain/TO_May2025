# How to provide the metadata

Please open the metadata.json file and fill in the required fields in the `Design` section.
Provide the final gds name, which should start with a prefix `FMD_QNC_`. The gds file should be placed in 
the `desing_data/gds` directory. 
The top level cell name should be consistent with the file name.
The values of Width and Height can be taken directly from the sealring. 

Do not edit any other fields in the file.

# How to provide the design data

While saving the gds file using `File->SaveAs` please use the following settings.

![KlayoutSave](../drc/klayout_save.png)




