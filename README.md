# ALERT
>- **VERY IMPORTANT** - Guide on running the application : shorturl.at/rsPR4 
>- **Disclaimer** - The game is developed by https://github.com/hirish99/Frogger-Arcade-Game, I refactored most of the codes and added a few more features. 
>- Details of refactoring work and added features are mentioned below.
>- This project is done as one of my Year 2 module assignment in University of Nottingham, Malaysia.

# EXTENSION
*All extensions made are for the purpose of providing convenience and better player experience*
>- **GAME MENU**
>
>>- **MenuScene.java** is the class to create START screen
>>- Contains 4 buttons ,**PLAY** ,**MANUAL** ,**BGM** ,**EXIT**
>> <img src="https://user-images.githubusercontent.com/61282110/175561953-e3b78e3a-4b29-4a9f-8d25-552923c74554.png" width="500" height="300">


>- **PLAYER GUIDE**
>
>>- **ManualScene.java** is the class to create INFO screen and also 2 buttons, **BACK TO MENU** and **EXIT**.
>> <img src="https://user-images.githubusercontent.com/61282110/175563161-866f4112-4417-4dec-83d8-d16a098b19fc.png" width="500" height="300">

>- **INTERESTING LEVELS ADDED**
>
>>- Original game behavior was slightly altered which is now **EasyScene.java**
>>- two new levels are added , **MediumScene.java** and **HardScene.java**
>>- **Snake.java**: a new obstacle that appears only in medium and hard mode
>>- **Frog.java**: 
>>
>>>- added animation and condition for death by snake
>>>- conditional statements for frog to move same speed and direction as safe platforms
>>- **Turtle.java** and **WetTurtle.java**:
>>
>>>- added animation for turtles to swim towards right 

>- **PERMANENT HIGH SCORE LIST IN TXT FILE**
>
>>- **ScoreHandler.java** and **AnimationHandler.java**: txt files are used to store scores permanently e.g. scoreboard.txt

>- **POP UP OF HIGH SCORES AT END OF EACH ROUND**
>
>>- **ScoreHandler.java** and **AnimationHandler.java** :When game over,a window pops up to show current score and top 5 highest score ever recorded
>>- **BubbleSort.java**: Sort scores in descending order

>- **PAUSE FEATURE**
>
>>- **GameSceneButtons.java** and **PauseLayer.java**:
>>
>>>- **PAUSE** to generate PAUSE screen with 3 buttons: **RESUME**,**BACK TO MENU** and **EXIT**
>>> <img src="https://user-images.githubusercontent.com/61282110/175563991-a7ded0b8-e26d-49f6-abb9-4f55c5c72250.png" width="300" height="500">

>- **BACK TO MENU AND AUTO SAVE FEATURE**
>
>>- **BACK TO MENU** in PAUSE screen goes back to START screen while automatically saving the progress in the game

>- **CHOOSE BACKGROUND MUSIC**
>
>>- **MenuScene.java** and **Bgm.java**:
>>
>>>- **BGM** in START screen drops 3 buttons for background music choice

>- **UNIT TESTING**
>
>>- Unit testing with Junit5 and TestFX framework, test files all in src/test/java  

>- **CLASS FOR BUTTONS**
>
>>- **Button.java** is used for creating buttons in any pane

>- **NEW ICON AND TITLE for GAME GUI**
 


# REFACTORING

>- Extract class/ Replace method with method object
>
>>-  Extracted **AnimationHandler.java** to replace createTimer() method in **FroggerApp** because method is too long
>>-  Extracted **EasyScene.java** from **FroggerApp.java** because **FroggerApp.java** act as **Main.java** where all scenes and sprites are aggregated
>>-  Obey single responsibility principle

>- Data Encapsulation
>
>>- All fields and objects in all classes are private
>>- Setter and getter methods are the only accessors to obey Object Orientation core concept 

>- Extract Interface
>
>>- FroggerApp class has an interface,**Launchable.java**
>>- Program to an interface not implementation

>- Factory Method Design Pattern
>
>>- **SceneFactory.java** and **SpriteFactory.java** are factory classes with static methods that create scenes and sprites respectively
>>-  Factory Method is used to create different objects without necessarily knowing what kind of object it creates or how to create it and also to centralize creation of similar objects


>- Organize codes according to MVC Pattern
>
>>- Reorganize all codes in each class into blocks of Model , View and Controller
>>- Increase readability and comprehensiveness of codes

>- Extract methods
>
>>- Extract **prepareMP()** from **playMusic()** 
>>- Extract methods **buildFrogHome()**, **buildLogs()**, **buildTurtles()** and **buildVehicles()** from constructors in EasyScene, MediumScene and HardScene
>>- Obey Single Responsibility principle 

>- Replace aggregation/composition with inheritance
>
>>- Created **ScoreHandler.java** to aggregate in **AnimationHandler.java**
>>- **Bgm.java** aggregate in **GamePane.java**
>>- Promote loose coupling and obey Composite Reuse principle

>- Consolidate duplicate conditional fragments
>
>>- Move identical codes out of each branches of a conditional to remove duplicated codes:
>>- **Frog.java**: **setSecond()** in **handle(KeyEvent)** 
>>- **WetTurtle.java**: **setSunk()** in **act(long now)**

>- Pull up method
>
>>- Pull up method **act(long now)** to **Sprites.java** to avoid code duplication

*visit javadoc for detailed information*
