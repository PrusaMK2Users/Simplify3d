# Simplify3d
Here you can find community sourced Simplify3d FFF profiles. These are free to use and share.

## Bed STL

To setup the bed STL:

Find the savedState.factory file
- OSX

        /Users/<your username>/Library/Application Support/Simplify3D/S3D-Software/

- Windows 10

        C:\Users\<your username>\AppData\Local\Simplify3D\S3D-Software\

- Linux

        ~/.local/Simplify3D/S3D-Software/


Place the `Heatbed-MK42.stl` for the bed model you want to use in the same folder as the savedState.factory file.

Export your current FFF profile
    - See the "To save your FFF Process Settings" section of the [Simplify3D instructions](https://www.simplify3d.com/support/articles/working-with-file-types/)
    - Once you have saved the FFF profile, delete the profile (we will re-import it in a later step)

If Simplify3D is open, close it.

Edit the FFF file you saved above in any text editor.

Look for `<overridePrinterModels>0</overridePrinterModels>` and ensure it looks like `<overridePrinterModels>1</overridePrinterModels>`. It should have value of 1.


Look for `<printerModelsOverride></printerModelsOverride>`

Replace that line with `<printerModelsOverride>Heatbed-MK42.stl</printerModelsOverride>` and save the file.

Open S3D again and import the FFF Profile you just saved.

You may want to turn off the build plate visualization so you can see the model of the bed beneath it. To do that open the S3D preferences (not the print process settings) and select the 'Visualization' tab. Then make sure that 'Include build table in virtual environment' is not checked.

You should now see the build platform, and should be able to use it to place your objects on the bed to avoid the mounting screw locations, or other print surface defects you may have.