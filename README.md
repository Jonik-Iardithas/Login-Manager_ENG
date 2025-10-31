**Update 30.10.2025:**

• The Login Manager now comes with an alternative Layout, which can be activated in the INI (see screenshots).\
• Shortcuts to important program files have been implemented, among others to the INI-file, making tedious file-browsing unnecessary.\
• The app now provides a facility for changing a once entered Master Password.\
• There have been plenty of small improvements in terms of user-friendliness.

**Hello world,**

I spent most of the summer of 2024 writing two applications in powershell. I had the idea for this project for quite some time, but it was only then that I found the right starting point for it. One application was meant to involve the encryption of login-data, the other one was for incremental backups. Soon I realised that this project was about more than just scripting, unexpectedly I entered the realm of application development. I'm entirely positive about the results and since their completion I use my applications on a daily basis. For that reason I would like to share my works with as many users as possible. Furthermore these scripts can serve as a reference work to others who are in the process of learning powershell, as they are rather straight forward.

So to the apps then...

The [Login-Manager](https://github.com/Jonik-Iardithas/Login-Manager_ENG/) creates and uses a json-file for data storage. The data itself is AES-encrypted. It uses a master password to access the data. Once in memory, the weakest part, as with many encryption programs, is that the memory can be read out and the data, including passwords, can be stolen. I searched the RAM after closing the app and couldn't find any remnants in memory. So to make sure to leave no traces, one has to close the app after usage (now happens automatically after the expiration of a certain time).

The [Backup-Maker](https://github.com/Jonik-Iardithas/Backup-Maker_ENG/) as its name implies, creates backups, more precisely incremental ones. This saves a lot of time compared to full backups, especially when using low speed USB-devices. Subsequently there is the option to generate a file protocol that lists all transfers in a proper manner. Important: In its current version Backup-Maker is only capable of saving folders (including subfolders), not entire drives. This feature may be added later. Note: The backup function runs in a seperate runspace, adding to the overall performance.

I tinkered install-scripts for the apps, because they require a certain file-structure to work. There are no changes to the registry, just creation and copying of files and folders, and optionally the creation of shortcuts. At the bottom of this readme you find a list of the changes made.

To make the whole thing a bit more aesthetic I added custom icons that can be selected during the installation process as required. By default the icon directory can be found at

`C:\Program Files\PowerShellTools\Login-Manager\Icons`

**Installation instructions:**

Download the complete archive at `Zip/ALL/` and expand it, so that there is `Install.ps1` and the corresponding zip-archive. Afterwards right-click on `Install.ps1` and choose *"Run with PowerShell"*.

Some technical remarks: I make excessive use of the `+=` method! I'm well aware of the ongoing discussion around that theme. Just that much: I use windows powershell 5.1 and could not detect any performance issues related to this method. On the contrary it appeared that when using some of the highly praised alternatives, it resulted in measurable performance drops. Therefore, whoever feels repelled by the `+=` method should avoid my scripts (or change attitude).

A final note on my own account: I'm just a self-taught hobby programmer, not a professional application developer. For that reason I ask you to go easy on me.

---

The following files are created resp. copied during the installation process:

Ini-files:

`C:\Users\%username%\AppData\Local\PowerShellTools\Login-Manager\Settings.ini`

Shortcuts (optional):

`C:\Users\%username%\Desktop\Login-Manager.lnk`\
`C:\Users\%username%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\PowerShellTools\Login-Manager\Login-Manager.lnk`\
`C:\Users\%username%\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\PowerShellTools\Login-Manager\Uninstall (Login-Manager).lnk`

Directories with icons and script-files:

`C:\Program Files\PowerShellTools\Login-Manager`\
`C:\Program Files\PowerShellTools\Login-Manager\Login-Manager.ps1`\
`C:\Program Files\PowerShellTools\Login-Manager\Uninstall.ps1`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Add.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Close.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_CMI_Open.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Del.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Edit.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Enter.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Exit.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Find.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Metadata.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Metadata_TB.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_MPW.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_MPW_Change.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_MPW_Change_TB.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_MPW_TB.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Next.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Open.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Open_TB.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Plain.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Prev.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_PW_Generator.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_PW_Generator_TB.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Icon_Reset_TB.png`\
`C:\Program Files\PowerShellTools\Login-Manager\Icons\Login-Manager.ico`

---

![Login-Manager_Screenshot](https://github.com/Jonik-Iardithas/Login-Manager_ENG/blob/main/Img/Login-Manager_ENG.png)
<br>
![Login-Manager_Screenshot](https://github.com/Jonik-Iardithas/Login-Manager_ENG/blob/main/Img/Login-Manager_ENG_TB.png)
<br>
![Login-Manager_Screenshot](https://github.com/Jonik-Iardithas/Login-Manager_ENG/blob/main/Img/Settings_TB.png)
