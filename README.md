# OT0 Editing Job Skillset Tutorial
A guide compiling information to easily create custom skill sets for characters in Octopath 0. Includes Unpacking .pak files, .uasset into json, json to .uasset, and repacking .pak files. This guide was done with Windows OS in mind.

**Disclaimer**: This tutorial only handles editing class skillset and extracts a simplified .pak to ease the modding process. This guide does not include class weapon changes, sprite changes, or editing the individual skills themselves. To do other types of modding for OT0, you must unpack **pakchunk0-Windows.pak** found in your *'...\Octopath_Traveler0\Octopath_Traveler0\Content\Paks'* game directory using the AES key found in the Octopath modding Discord: https://discord.gg/t43Kbrp. More details of this can be found at the bottom of this page.

## Tools Needed:
* [repak](https://github.com/trumank/repak) (Unpacker)
* [UAssetMessagePack](https://drive.google.com/file/d/1drP7k3QOLzK0cEkApgWZP1q0kj2NYdnS/view?usp=sharing) (UAsset to and from Json files) by @igoticecream
* [UnrealPak](https://github.com/Dmgvol/UE_Modding/raw/main/Tools/UnrealPak.zip) by FluffyQuack (Repack Uassets) 
* **SkillsUnedited_P.pak** (Provided file)
* **Mappings.usmap** (Provided file)
* [Octopath 0 Spreadsheet](https://docs.google.com/spreadsheets/d/1yCGuadxkicFMeCBzncOI5o1wlfeRk4KPxpHM4aZa7VE/edit?gid=0#gid=0)
* Any text editor, such as Notepad++

**Example**:

<img width="351" height="312" alt="image" src="https://github.com/user-attachments/assets/cecb0642-e993-4f8a-a568-f6f031859058" />


## Setup:
**(1)** Download the 3 tools above and extract their files above into seperate folders, in a modding directory of your choosing. Download the two files above from this repository.

**(2)** Create another folder of any name and place **Mappings.usmap** file inside it. (I.e directory: ...\Octopath 0 Modding\Tools\Mapping File\Mappings.usmap).

## Unpacking:

**(3)** Place **SkillsUnedited_P.pak** file into the **repak** folder.  Open command line by typing *cmd* in the folder directory and press enter. Type or paste the following command into cmd: *repak.exe unpack SkillsUnedited_P.pak*.

<img width="700" height="41" alt="0" src="https://github.com/user-attachments/assets/bcff478b-c1df-49c3-9249-f6b02e05c738" />

<img width="977" height="198" alt="1" src="https://github.com/user-attachments/assets/80c69764-b6ea-4adc-8584-2ff3aeede1dd" />

<br/><br/>
**(4)** Navigate the newly extracted pak folder *'...\SkillsUnedited_P\Octopath_Traveler0\Content\Local\DataBase\SkillBoard'* and copy **SkillBoardData.uasset** & **SkillBoardData.uexp** into the **UAssetMessagePack** folder.
<br/><br/>

**(5)** Open *cmd* in the **UAssetMessagePack** directory and input the following command: *UAssetMessagePack.exe tojson SkillBoardData.uasset SkillBoardData.json VER_UE5_4 "YourMappingDirectoryHere\Mappings.usmap"*. Make sure to write your actual directory. You can obtain this by clicking on the directory bar of your Mapping File to copy the directory.

<img width="447" height="32" alt="image" src="https://github.com/user-attachments/assets/16462afb-b510-497d-9cf1-db597e156b31" />

<img width="977" height="188" alt="2" src="https://github.com/user-attachments/assets/c1ed1f24-c68b-4a5f-9519-f3d80806b71e" />

<br/><br/>
## Editing the Skills:

**(6)** Open the resulting **SkillBoardData.json** with any text editor and make your desired changes. This is where you edit protagonist jobs and character's skillsets. Search for the *m_id* of the job or character you want to edit (see below). *m_SkillID* has 7 codes for learnable skills and *m_SupportSkillID* for the 4 job passives. *m_CanNotSupport* controls whether skill can be mastered or not using JP. It is possible to add more than 7 skills and 4 passives (currently unknown consequences). You can also make all character's skills learnable if you desired.

Use the OT0 Spreadsheet as a reference. The order of skills there matches the order of skills found in the json for each individual character.
https://docs.google.com/spreadsheets/d/1yCGuadxkicFMeCBzncOI5o1wlfeRk4KPxpHM4aZa7VE/edit?gid=0#gid=0

__For example__: if you want the "Almighty" buff skill (Phys atk/Phys def/Elem atk/Elem def), cntrl-f search **2047** (Sazantos) and nab the his third skill (as seen on the OT0 spreadsheet). This translates into the skill id 901351. cntrl-f your desired job id found below and place 901351 into one of your skill slots. 

<img width="889" height="251" alt="image" src="https://github.com/user-attachments/assets/91023654-cfce-403d-9ddc-b387cd5a5d11" />

<img width="1154" height="604" alt="3" src="https://github.com/user-attachments/assets/5f3be80d-831b-4e70-926b-e6a91502d020" />
<br/><br/>

*Note*: the voice line associated for the original skill will still play the same audio, regardless if it is changed to something else, silimar to OT2. This requires seperate modding that can be discussed in the Discord server.
<br/><br/>

**(Special thanks to @Kermit for these id documentations)**:

* 901 - warrior
* 902 - apothecary
* 903 - thief
* 904 - scholar
* 905 - cleric
* 906 - hunter
* 907 - merchant
* 908 - dancer
<br/><br/>
* 2015 - Viator
* 2016 - Reime
* 2017 - Ludo
* 2019 - celsus
* 2020 - Heidne
* 2021 - Esperre
* 2022 - Macy
* 2023 - Phenn
* 2024 - Delitia
* 2025 - Pius
* 2026 - Laurana
* 2027 - Xerc
* 2028 - Alexia
* 2029 - goodwin
* 2030 - Saoirse
* 2031 - Olberic
* 2035 - Hannit
* 2038 - Primrose
* 2043 - Eltrix
* 2044 - Rondo
* 2045 - Tatloch
* 2046 - Stia
* 2047 - Sazantos

*Note*: This list is not finished and can be updated overtime. An easy way to find a missing id is to cross reference *m_CanNotEssential* data with the OT0 spreadsheet. 

**For example**: Suppose Hannit is not yet listed. Hannit's *m_CanNotEssential* True and False values follows FTFFFFF (skills), FTTT (passives). We can see in the list above Olberic's character id is 2031 and therefore a liklihood Hannit is after him. Search for a pattern FTFFFFF, FTTT in the JSON and we discover id 2035 matches this pattern. After repacking and loading the game, this is confirmed to be Hannit. Note that this method is not foolproof, as for example Stia and Primrose follow the same mastery pattern of FFFFFFT, FTTT and can be accidentally confused for one another.

## Repacking:

**(7)** Use *cmd* in the **UAssetMessagePack** directory and use the command: *UAssetMessagePack.exe fromjson SkillBoardData.uasset SkillBoardData.json SkillBoardData-from-json.uasset VER_UE5_4 "YourMappingDirectoryHere\Mappings.usmap"*. Make sure to place your actual directory.

<img width="982" height="192" alt="4" src="https://github.com/user-attachments/assets/d0c0b71f-e63c-4c9e-9dc6-6ddc32bf8bd5" />
<br/><br/>

**(8)** Copy **SkillBoardData-from-json.uasset** and **SkillBoardData-from-json.uexp** back to the **repak** folder, into *"...\SkillsUnedited_P\Octopath_Traveler0\Content\Local\DataBase\SkillBoard"* directory. Rename both files into **SkillBoardData.uasset** & **SkillBoardData.uexp** and overwrite the old files.
<br/><br/>

**(9)** Copy/move the entire **SkillsUnedited_P** folder (with its folder structure intact and nothing but the two files updated) into **UnrealPak** folder. Rename **SkillsUnedited_P** folder into **"Exports"**. Drag and drop the **Exports** folder into **UnrealPak-Without-Compression.bat** to get your .pak file.
<br/><br/>

**(10)** Rename your **Exports.pak** file into anything you wish, THEN append a **_P** at the end (I.e SkillsEdited_P.pak). Copy and paste your pak file into your OT0 game directory: *"...\Octopath_Traveler0\Octopath_Traveler0\Content\Paks"*. Load up your game and you're done! Test to see if your mod works.
<br/><br/>

## Side section: Unpacking pakchunk0-Windows.pak

If you wish to use the full game directory instead of the simplified .pak for other modifications, use the following *cmd* command for **repak**, as detailed on the Discord: **repak.exe --aes-key='0x14A2B6A734EE06B2B011E847AFFCD1DB9CB46C049B1AA5E3F44CCFE332EF6CDA' unpack --output '.\Dumps' 'C:\Program Files (x86)\Steam\steamapps\common\Octopath_Traveler0\Octopath_Traveler0\Content\Paks\pakchunk0-Windows.pak'**. Adjust the directory as needed.

If this command does not work, try using the following command: **repak.exe --aes-key 0x14A2B6A734EE06B2B011E847AFFCD1DB9CB46C049B1AA5E3F44CCFE332EF6CDA unpack pakchunk0-Windows.pak**.

**Note**: this process may take a while to unpack.
<br/><br/>

## Special Thanks to the OT0 Modding Discord:
*  @igoticecream - Pioneer into OT0 modding and integeral UAssetMessagePack tool developer.
*  @Kermit - For their early documentation of character/job ids and process clarifications.
