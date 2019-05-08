
## PowerView Aggressor Script for CobaltStrike 

##### A user menu for [@harmjoy's](https://twitter.com/harmj0y) [PowerView](https://github.com/PowerShellMafia/PowerSploit/blob/dev/Recon/PowerView.ps1)
##### and [SharpView](https://github.com/tevora-threat/SharpView)

##### Updates:
   * Cleaned up code
   * Added powershell-import check to see if PowerView is imported or not, it if doesn't detect PowerView it will import it for you. By default it will search the directory where the aggressor script is located to import but it can be changed. Same goes for SharpView.
   * Added PSInject that will use the current beacon's PID and architecture to prevent remote process injection. Be aware if using PSInject and killing a job it will kill the beacon, so best to let it finish to keep beacon alive
   * Now that powerpick, psinject, and execute-assembly use the current beacons token when specifying a credential it will no longer be part of the command but rather a token will be created in Cobalt Strike then the cmdlet will be executed

TODOs:
   * NTLM and kerberose usage so you aren't required to have only plain text creds
   * PowerShell pipeline with cmdlets

##### Very similar to the PowerView v2 [aggressor script](https://github.com/tevora-threat/aggressor-powerview)

All functions listed in the PowerView about page are included in this with all arguments for each function.

![powerview1](https://user-images.githubusercontent.com/9096315/43167904-31311bf4-8f50-11e8-9c89-1b86fb69e5ff.png)

Has the ability to accept credentials (format: domain\user password to parse correctly) 

![powerview2](https://user-images.githubusercontent.com/9096315/43167890-2d9f74e0-8f50-11e8-80e9-c994c54eb56b.png)

With SharpView now has the ability to leverage execute-assembly and like before PowerPick and PowerShell

![powerview3](https://user-images.githubusercontent.com/9096315/43167896-30078ca4-8f50-11e8-9a6c-dcd333ddae1b.png)


Now has a help menu that provides the description and Parameters from the PowerView.ps1 source

![powerview4](https://user-images.githubusercontent.com/9096315/43167905-31f7ae72-8f50-11e8-93b0-edb1df5b16f7.png)


~~The script does not automatically do powershell-import for PowerView you must manually do that first. Additionally, depending on your placement of SharpView you may need to change the location in the $sharpviewlocation variable.~~

Please note this requires PowerView 3.0 (current dev branch) and SharpView (only version)
