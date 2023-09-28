# Convert ebook to KFX

Newer Kindle ebook readers support better typography when using the "KFX" format. 
In particular I need ragged margin, as the hypenless justification I usually get when converting text to read on the Kindle
introduces jarring word gaps that make text very hard to read.

## Windows Explorer context menu

I don't want to use calibre with the GUI (I prefer managing files manually), but it has a useful KFX Output plugin.
To add this to the windows explorer context menu to convert ebooks to KFX:

Install calibre and Kindle Previewer 3. In a shell run

```sh
calibre-customize -a KFX_Output.zip
```

on the downloaded plugin zip file to install the plugin.
Then add

```bat
@echo off
"C:\Program Files\Calibre2\ebook-convert.exe" "%~1" "%~dpn1.kfx" --output-profile="kindle_pw3"
```

to `C:\Users\[Your Username]\AppData\Roaming\Microsoft\Windows\SendTo` in a file `ConvertToKFX.bat`.
Now it should be possible to use the `Sent To` context menu to convert file for the Kindle reader.
