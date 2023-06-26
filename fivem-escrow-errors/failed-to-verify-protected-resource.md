# 🛡 Failed to verify protected resource

Example of an Error Message: Lacking the required entitlement for `E-Jobads`. Potential Causes

* There's no .fxap file present in the script folder.
* You are utilizing Filezilla.
* Your server hosting is deploying Filezilla to upload the script.
* You're uploading the folder to the VPS file by file. Instead, upload the .zip file and uncompress it after it's already on your VPS (drag and drop the zip file, not the folder).

Proposed Solutions

* Re-download the script from the[ FiveM keymaster](https://keymaster.fivem.net/).
* Use [WinSCP](https://winscp.net/eng/download.php) for script uploading instead of Filezilla.
* Reboot the server.
