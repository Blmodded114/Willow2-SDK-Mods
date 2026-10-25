A library to make registering custom characters simpler. Supports Borderlands 2 and AoDK, will test Borderlands the Pre Sequel later.

Registration arguments (all are strings):
```
mod_name (used for the default paths. Probably not needed with custom paths but I haven't tested that) 
character_name: str (character name)
custom_suffix (fallback incase the character name is already taken)
package_path (path to the DownloadablePackageDefinition. Defaults to  f"{mod_name}.PackageDef_Players")
character_path (path to the DownloadableCharacterDefinition. Defaults to f"{mod_name}.CharacterDef_Players")
class_path (path to the PlayerClassIdentifierDefinition. Defaults to f"{mod_name}.PlayerClassId_{character_name}")
name_path: (path to the PlayerNameIdentifierDefinition. Defaults to  f"{mod_name}.PlayerNameId_{character_name}")
boosted_name_path (Bl2 exclusive, used for a boosted character and uses a second PlayerNameIdentifierDefinition. Defaults to f"{mod_name}.PlayerNameId_{character_name}30")
```

Registering a character, using Hallowed Characters as an example:
Step 1: import the register character function
```
from char_loader import register_character
```
Step 2: choose whether to use the default paths or custom ones. Then do the following per custom character:
registering a character with the default paths:
```
register_character(mod_name="HallowedCharacters", character_name="Krug", custom_suffix="OrcChief")
```
registering a character with custom paths:
```
register_character(
    mod_name="HallowedCharacters", 
    character_name="Krug", 
    custom_suffix="OrcChief",
    package_path="HallowedCharacters.PackageDef_Players",
    character_path="HallowedCharacters.CharacterDef_Players",
    class_path="HallowedCharacters.PlayerClassId_Krug",
    name_path="HallowedCharacters.PlayerNameId_Krug",
    boosted_name_path="HallowedCharacters.PlayerNameId_Krug30"
)
```
