/\*<!\[CDATA\[\*/ div.rbtoc1718320106430 {padding: 0px;} div.rbtoc1718320106430 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320106430 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [Overview](#ChangingCharacters-Overview)
*   [Character Model Swapping](#ChangingCharacters-CharacterModelSwapping)
    *   [Inverse Kinematics Character Controller](#ChangingCharacters-InverseKinematicsCharacterController)
*   [Custom Animations](#ChangingCharacters-CustomAnimations)

Overview
========

This section provides detailed instructions on how you can switch out the demo character model for a model for your game. Documentation has also been provided to explain some Caveats you may find when using the **Character Controller Plus** package and how you can work around these caveats.

Character Model Swapping
========================

Below explains how you can swap the demo character Human (Baal) with your very own Character model **Character Controller Plus** package.

Assuming you have a fully rigged model and have imported the model into your project the following steps should be followed to update the character model.

1.  Either clone the demo character prefab or simply use the existing character prefab. In this example, I have cloned the existing non-IK Character Controller.
    
2.  First, enter the prefab view of the Character Controller prefab and remove the demo character Human (Baal).
    
3.  Next we can simply edit the prefab and drop your character model under the root Game Object of the prefab. At this point, your project should look similar to the image below. The only difference should be that your provided character appears where Human (Baal) once was.
    

![image-20240416-223132.png](attachments/65554/10682369.png?width=760)

4.  If your character was imported with an animator, now is the time to remove it as we source our animations from the root Character Controller game object and the **Character Controller Plus** package already has one setup for you.
    
5.  Before you update the animator configuration you will need to head to your character model (Imported Character Asset) in your Project view. Here select your character model and enter the Rig tab in the inspector and select the “Create From This Model” option in the Avatar Definition option. You will also need to set the Root node to match the root bone of your rig. Once completed, go ahead and apply your changes which will create an **Avatar** object nested within your character model.
    
    1.  If you choose to continue to use the provided **Rig**, the correct Root node to select is the “metarig/spine” bone.
        

![image-20240416-223943.png](attachments/65554/10649603.png?width=760)

6.  Now, select the root Character Controller and navigate to the Animator component in the inspector. Update the Avatar configuration with your newly created Avatar.
    

![image-20240416-224114.png](attachments/65554/10878977.png?width=760)

7.  At this point you can drop your character into your scene and hit play. Your Character should be fully animated and may require some needed adjustments like updating the character position to fit within the bounds of the Character Controller along with some potential changes to your state configuration(s). It may require some tweaking to get things just right. Please consult [State Definition](State-Definitions_131196.md) documentation for more information regarding further **Character Controller Plus** configuration topics.
    

### Inverse Kinematics Character Controller

When using an IK setup, additional adjustments may need to be made to place your IK targets and hints according to the anatomy of your Rig, along with any constraint settings you wish to deploy. Consult Unity’s [Animation Rigging](https://docs.unity3d.com/Packages/com.unity.animation.rigging@1.2/manual/index.md) documentation for more information.

If you choose to not use the IK setup by either using the non-IK prefab or by simply removing the IK components of the Character Controller, you may notice errors regarding a missing receiver for various animation events. To stop these errors from occurring, you can do either of the following:

*   Remove the animations events from each of the animations that are reporting the missing receiver issue.
    

![image-20240327-040428.png](attachments/65554/3801123.png?width=760)

*   Add the AnimationEventIKHandler script to the root Character Controller game object. This will allow the animation events to be consumed but will not do anything as there are no IK components to interact with, this of course will minimally impact performance for no apparent gain, so it is best to just remove the animation events.
    

Custom Animations
=================

If you wish to create your own custom animations you will need to be sure that each custom animation uses the same rig/bone structure as your Skinned Mesh Renderer component(s). This means that if you choose to provide your own animations, all animations will need to contain the same bone structure.

If you prefer to use **Mixamo** to rig your models, you can simply import the FBX you download from **Mixamo** into your preferred modeling/animating software and edit your animations this way, that way you can ensure that your animation files follow the same rig/bone structure as the animation files provided with the demo character (Dark Bot).

![image-20240327-031946.png](attachments/65554/3768340.png?width=760)