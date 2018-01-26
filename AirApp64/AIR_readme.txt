AIR 64bit for desktop instructions

1. Download 64bit AirSDK from https://labs.adobe.com/downloads/air.html and install to
	AIRSDK_Compiler_28_112
	
2. Create AIR AS3 Projector project.

3. Set SDK path in Project->Properties->SDK.

4. In Project->AIR App Properties:
	Installation->Supported Profile->Extended Desktop (ONLY)

5. Copy OpenFinAirNativeExtension64.ane to lib directory, copy the file to 
	OpenFinAirNativeExtension64.zip, unzip to a folder, rename folder name
	to com.openfin.OpenFinNativeExtension.ane

6. In Project->AIR App Properties:
	Extensions: Browse and Add 64bit native extension
	
7. Open application.xml and update:
	<application xmlns="http://ns.adobe.com/air/application/28.0">

8. on Project tree panel, right-click the native extension and select "Add to Library".

9. Modify RunApp.bat and add -extdir

	adl "%APP_XML%" "%APP_DIR%" -extdir lib

10. Configuration

	- edit 'bat\SetupSDK.bat' for the path to Flex SDK (defaults should be ok)


11. Creating a self-signed certificate:

	- run 'bat\CreateCertificate.bat' to generate your self-signed certificate,

	(!) wait a minute before packaging.


12. Run/debug from FlashDevelop as usual (build F8, build&run F5 or Ctrl+Enter)


13. Packaging for release:

	- run 'bat\PackageApp.bat' to only create the AIR setup
	
	
