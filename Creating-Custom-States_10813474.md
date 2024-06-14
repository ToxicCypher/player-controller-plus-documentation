/\*<!\[CDATA\[\*/ div.rbtoc1718320124879 {padding: 0px;} div.rbtoc1718320124879 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320124879 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [Overview](#CreatingCustomStates-Overview)
*   [How To](#CreatingCustomStates-HowTo)
    *   [Create State File](#CreatingCustomStates-CreateStateFile)
        *   [Cloning Template](#CreatingCustomStates-CloningTemplate)
        *   [Base State Reference](#CreatingCustomStates-BaseStateReference)
        *   [PlayerState References](#CreatingCustomStates-PlayerStateReferences)
        *   [Verify Changes](#CreatingCustomStates-VerifyChanges)
    *   [Animator Update](#CreatingCustomStates-AnimatorUpdate)
        *   [Add Animation Parameter](#CreatingCustomStates-AddAnimationParameter)
        *   [AnimationMap Class Update](#CreatingCustomStates-AnimationMapClassUpdate)
        *   [Using AnimationMap Parameters](#CreatingCustomStates-UsingAnimationMapParameters)
        *   [Setting Animation Transitions & Clip](#CreatingCustomStates-SettingAnimationTransitions&Clip)
    *   [Input System Update](#CreatingCustomStates-InputSystemUpdate)
    *   [Implementing State Checks](#CreatingCustomStates-ImplementingStateChecks)
    *   [Implementing Custom Logic](#CreatingCustomStates-ImplementingCustomLogic)

Overview
========

For full disclosure, this section will require that the developer has at least some experience writing code in Unity using C#.

In this section, we will be exploring the topic of developer created custom states. The Player Controller Plus package is entirely extensible, granting the developer the ability to hook into the state machine and provide their own transitions.

How To
======

This section will go over the core topics related to creating your own custom states and all of the areas of your project that each custom state will require updates in. Sections will be listed below, detailing each particular step needed to setup each custom state. For greater readability, steps will be listed in chronological order.

### Create State File

#### Cloning Template

1.  The first step to creating your custom state is to first clone the provided template state file, which can be found here `..\Character Controller Plus\Demo Character\Scripts\State Manager\Templates\TemplateState.cs.`
    
2.  With the state cloned, you can place the file anywhere but for organizational purposes, place the file in the `..\Character Controller Plus\Demo Character\Scripts\State Manager` directory.
    
3.  Rename the file to a title that represents the state that is represented by the state, the convention that Character Controller Plus assumes is as follows: `Player<Present Tense Action>State.cs`.
    
4.  If your IDE did not ask to automatically update your class name, do this now.
    

There are a handful of commented out lines in your new state to circumvent compiler errors, but we will come back to this as we will need to setup a couple of things before we can uncomment the code without those pesky compiler errors.

![image-20240420-013408.png](attachments/10813474/14647316.png?width=760)

#### Base State Reference

1.  Next, we will need to reference this new state inside of the PlayerControllerPlus.cs base state class. This will allow you to access serialized parameters within the Player Controller Plus component on your character, making it easy to test your parameter configuration at run-time.
    
2.  In `..\Character Controller Plus\Demo Character\Scripts\State Manager\CharacterControllerPlus.cs` add your custom state under the State Definitions header.
    

![image-20240420-015030.png](attachments/10813474/14581770.png?width=760)

#### PlayerState References

1.  Next you will need to add your new state type to the PlayerState enum and a couple of related functions. Navigate to the `..\Character Controller Plus\Demo Character\Scripts\State Manager\State Manager Parameter Store\PlayerState.cs` class and add your new state name to the list of available PlayerState’s.
    

![image-20240420-015706.png](attachments/10813474/14450702.png?width=760)

2.  Back in `..\Character Controller Plus\Demo Character\Scripts\State Manager\CharacterControllerPlus.cs` there are two functions to update with details to follow.
    
    1.  In the DetermineState function add a case statement that will map your custom state class to the PlayerState enum.
        
        1.  ```
                    public PlayerState DetermineState(PlayerBaseState state)
                    {
                        switch (state)
                        {
                            case (PlayerDancingState):
                                {
                                    return PlayerState.Dancing;
                                }
            ```
            
    2.  In the DetermineStartingState function add a case statement that will map the selected starting state to your custom state module.
        
        1.  ```
                    private void DetermineStartingState()
                    {
                        switch (startingState)
                        {
                            case (PlayerState.Dancing):
                                {
                                    currentState = DancingState;
                                    break;
                                }
            ```
            

#### Verify Changes

Save your changes and head to the Unity Editor and you should see your new state appear in the Character Controller Plus component on your character.

![image-20240420-015219.png](attachments/10813474/14450694.png?width=760)

### Animator Update

#### Add Animation Parameter

1.  Next, you will need to open the Animation Controller assigned to the Animator attached to your character.
    
2.  Once in the Animator view, select the Parameters tab and select the '+' button. This will ask which type of parameter you would like to add, select bool.
    
3.  Rename the new bool parameter to match the format “is<Your States Action>”. This is purely a design choice as the name does not really matter.
    

![image-20240420-021037.png](attachments/10813474/14778394.png?width=444)

#### AnimationMap Class Update

1.  Back in the code base, navigate to the `..\Character Controller Plus\Demo Character\Scripts\State Manager\State Manager Parameter Store\PlayerAnimationMap.cs` class. Here we will be adding a static field which is equal to the name of the new Animator parameter we just added.
    
2.  Create a new static string variable and assign the parameter name to it.
    

![image-20240420-021327.png](attachments/10813474/14450716.png?width=760)

#### Using AnimationMap Parameters

1.  Back inside your custom state class we can start uncommenting some code. Both of the function calls to ApplyAnimation can be uncommented and the first parameter PlayerAnimationMap.template will need to be replaced with your new PlayerAnimationMap variable.
    

![image-20240420-021824.png](attachments/10813474/14778405.png?width=760)

#### Setting Animation Transitions & Clip

Now is the perfect time to identify all of the states that you wish for your new custom state to be able to transition to and from. For this example, I will only be allowing my character to transition to/from the Dancing state to/from an Idle state.

1.  Now we can add our animation clips and setup some animation transitions to our new state, so head back to the Unity Editor and in the Animator view, determine which Sub-State Machine best suits your new custom state.
    
2.  Add a new animation clip for your custom state animation.
    

![image-20240420-022411.png](attachments/10813474/14581790.png?width=760)

3.  Now based on your desired state transitions, you can begin drawing transitions to and from your custom animation clip.
    

![image-20240420-022531.png](attachments/10813474/14581797.png?width=760)

4.  You can configure the animation transition setting by selecting a transition and making changes to them. I find that the following settings are a good start.
    
    1.  Has Exit Time → False
        
    2.  Interruption Source → Next State
        
5.  Finally, you will need to add Conditions as for when a transition should take place. Recalling the two ApplyAnimation functions that we uncommented previously, these two steps are responsible for setting the values of the Animator parameters to true or false depending on whether the state is entered or exited. That being said, under the Conditions section in your Animator transition settings, create conditions for your state.
    
    1.  My typical approach is to enter a state, I expect the previous state animator parameter to be false and the target state animator parameter to be true.
        

![image-20240420-023053.png](attachments/10813474/14942209.png?width=760)

Once your transitions are in place and configured, we can move onto the final piece of the initial setup.

### Input System Update

1.  Now that our animation transitions and our custom state class is setup, we will need to add some Input System configuration so we can actually control our character in this state.
    
2.  Navigate to the Player Input System in the Project table here `../Character Controller Plus/Services/Player Input System/Player/Player Input System.inputactions` and open the file. This will bring up the following menu.
    

![image-20240420-023506.png](attachments/10813474/14974978.png?width=760)

3.  First we will need to add a new Action Map by pressing the '+' button located at the top of the left-most column.
    
4.  Rename the Action Map to be suitable for the name of your custom state.
    
5.  Now, with your custom Action Map selected, create actions that you would like your custom class to perform. In the case of this example, I will simply be providing my custom class with the ability to move only.
    

![image-20240420-023752.png](attachments/10813474/14778419.png?width=760)

6.  Select the Save Asset button near the top of this window to save any changes you have made and head back into your IDE and open up your custom state class.
    
7.  In the OnEnableState() function, uncomment the code and replace each reference to Template with the name of your new Action Map.
    
8.  Perform the same tasks in step 7 in the OnDisableState() function.
    
9.  For each Input System Action that you have added to your new Action Map, you will need to write callback functions and subscribe to those callback functions when specified input is detected. There are plenty of examples in the code base for how to do this but for more information please consult Unity’s [Input System](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.7/manual/index.md) documentation.
    

![image-20240420-024550.png](attachments/10813474/14450750.png?width=760)![image-20240420-024438.png](attachments/10813474/14942219.png?width=760)

### Implementing State Checks

1.  At this point, our custom state is functioning, the only problem is, we have no way to transition into this state yet, so we will need to add a state check in each of the states that can transition to your custom state. In this example, I will only be transitioning from Idle to Dancing.
    
2.  In the `..\Character Controller Plus\Demo Character\Scripts\State Manager\PlayerIdleState.cs` class, navigate to the StateCheck() function.
    
3.  Here, we will add a developer defined condition that must be met, in-order for the player to transition into your custom state.
    

![image-20240420-025343.png](attachments/10813474/14450761.png?width=760)

4.  Now, the state can be transitioned to, but how do we exit the custom state. Similarly to the condition just added to the Idle state, we will need to supply an exit condition in the custom state.
    

![image-20240420-025548.png](attachments/10813474/14450770.png?width=760)

5.  Congratulations! You have setup your first custom state, all that is left to do at this point is add any custom logic to your custom state class that best suits the needs of your project. See the implementing custom logic section for generalize details on where custom logic belongs in your custom state module.
    

### Implementing Custom Logic

Custom state logic should be implemented in any of the Update functions, UpdateState(), LateUpdateState() and FixedUpdateState(). Where the logic goes is purely up to the developer as it completely varies depending on what sort of logic is implemented.