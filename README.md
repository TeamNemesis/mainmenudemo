# Main Menu Demo Documentation
Official documentation for the Main Menu Demo for Unity3D made by Team Nemesis.

### Index
1. Basic Configuration
2. Important notes
3. Source-code overview

## Credits
All used fonts are downloaded from 'www.dafont.com' and were licensed with permission for commercial use.

## What is included within this pack.
### Fonts:

    - Mostly Mono
    
    - Ninja Naruto
    
    - Qarmic Abridged
    
    - Teen
    
### Prefabs:

    - Block (used for decoration)
    
    - Main Menu UI
    
    - Pause Menu UI
    
    - Player
    
### Scenes:
    - Main Menu (This scene contains the main menu example)
    - Sample Scene (This scene contains the pause menu example)

### Scripts:

    - BlockBehaviour & BlockSpawner 
          -You can ignore these, these are used for the main menu background 
           but doesn't add any kind of functionallity to the product itself.
           
    - MainMenu 
          - Contains all the functionallity for the main menu.
          
    - PauseMenu 
          - Contains all the functionallity for the pause menu.
          
    - ResponsiveButton 
          - This is used to add a simple effect to the buttons when a user is hovering over it.
          
    - PlayerController
          - Powers the 'Player' prefab which is used in the 'Sample Scene' scene.
          
## Important Notes
### We recommend you to read these notes carefully, ignoring them may lead to disfunction of the product.   

Some main menu packs/tutorials may use the 'OnClick()' function which is by default attached to the button itself.
Since we wanted to add a more responsive feeling to the buttons, we had to use the 'Even Trigger' component which is attached to the text of the button.
Because of this the 'OnClick()' function may not work in some cases, and we'll recommend you to use the 'Event Trigger' component attached to the text of each button instead.

## Basic Configuration
### This section contains basic configurations for the main menu demo, do note that we won't explain how you can change the text of a button since this is basic Unity knowledge.

### User Interface (MainMenu.cs) Configuration:

        - Play Scene:
            - The 'Play Scene' defines the scene which will be loaded once the player presses the 'Play' button, this variable
            - has to be the integer of the scene which can be found in the 'Build Settings'.
            - We defaulted it to 1, since this is the integer of the 'Sample Scene' scene.
            
        - Checkbox;
            - The Checkbox GameObject variable is used to identify the checkbox icon used at the Fullscreen Toggle 
            - at the 'Settings' panel.
            
        - Game Version:
            - This Text variable is used to identify the text box used for game version.
            - The game version will be automatically updated to the current Project Version which can be changed at
            - 'Edit > Project Settings > Player > Version'

### ResponsiveButtons.cs Configuration:

            - We wanted to add a little bit of a responsive feeling to all of the buttons, because of this all buttons needed 
            - a little bit of configuration.
            - The 'ResponsiveButton' script should always be attached to the button itself, the text of
            - the button should contain the 'Event Trigger' component, and require the
            - 'Pointer Enter', 'Pointer Exit' & 'Pointer Down' Event Type which can be added by clicking on
            - "Add New Event Type".
            
                - Pointer Enter Configuration:
                    - Once you added the "Pointer Enter" Event Type, you have to add the parent button as the Game Object,
                    - and call the ResponsiveButton.Hover function from there.
            
                - Pointer Exit Configuration:
                    - Once you added the "Pointer Exit" Event Type, you have to add the parent button as the Game Object,
                    - and call the "ResponsiveButton.ExitHover" function from there.
            
                - Pointer Down Configuration:
                    - The configuration for the Pointer Down is kinda different, because we want to trigger an event that
                    - actually add's functionallity to the button.
                    - By default all of those events are stored in the MainMenu.cs script, which is attached to the 
                    - 'User Interface' by default.
                    - So in order to trigger a default event, we have to add the 'User Interface' as an object of
                    - the event, now we can call a function from the MainMenu.cs script thru the MainMenu.cs.
                    - (Examples: 'MainMenu.PlayButton' or 'MainMenu.QuitButton')
                    
### PauseMenu.cs Configuration:

            - The PauseMenu.cs is the script to power the Pause Menu (obviously).
            - This script contains 2 configurations. 
                 1. The first configurable thing is a GameObject Variable which is used to identify 
                    the Pause Menu itself, so it can be enabled or disabled 
                    whenever the player presses the Escape button.
                    
                 2. The second configurable variable is an integer to identify what scene has to be
                    loaded when the player clicks on the Exit Button.

## Source-code overview

