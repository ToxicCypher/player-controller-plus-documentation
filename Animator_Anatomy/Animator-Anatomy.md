
*   [Summary](#AnimatorAnatomy-Summary)
*   [Animation Layers](#AnimatorAnatomy-AnimationLayers)
*   [Animator Parameters](#AnimatorAnatomy-AnimatorParameters)
*   [Animator Sub-State Machines](#AnimatorAnatomy-AnimatorSub-StateMachines)
    *   [Base State Machine](#AnimatorAnatomy-BaseStateMachine)
    *   [Grounded Mobile Sub-State Machine](#AnimatorAnatomy-GroundedMobileSub-StateMachine)
    *   [Grounded Immobile Sub-State Machine](#AnimatorAnatomy-GroundedImmobileSub-StateMachine)
    *   [Aquatic Sub-State Machine](#AnimatorAnatomy-AquaticSub-StateMachine)
    *   [Airborne Sub-State Machine](#AnimatorAnatomy-AirborneSub-StateMachine)
    *   [Scaling Sub-State Machine](#AnimatorAnatomy-ScalingSub-StateMachine)
*   [Updating Animator Transitions](#AnimatorAnatomy-UpdatingAnimatorTransitions)
    *   [Summary](#AnimatorAnatomy-Summary.1)
*   [Updating Animator Parameters](#AnimatorAnatomy-UpdatingAnimatorParameters)
    *   [Introduction](#AnimatorAnatomy-Introduction)
    *   [Updating Parameters](#AnimatorAnatomy-UpdatingParameters)

Summary
=======

A fully built-out **Animator** mecanim has been created to manage animation transitions for you from the get go. The animator can be adjusted however you feel fit for your needs but it is important to keep the transitions intact as to not break any state transitions assuming your character is destined for the animation state in question.

Animation Layers
================

The provided **Animator** component only contains a single **Base Layer**.

Animator Parameters
===================

**Animator** Parameter names are not to be updated as they are referenced in code when state transitions occur. If you are interested in making changes, removals or additions to the **Animator** parameters, please see the Updating Animation Parameters section below.

The provided **Animator** uses only Boolean values which are used to transition between states. These values allow the Character Controller Plus State Machine to treat the Animator as an extension of the Character Controller Plus State Machine.

This is accomplished by setting the relative state Boolean value to true when entering a particular state and setting the value to false when exiting the state.

Animator Sub-State Machines
===========================

This section describes briefly the functionality behind each of the **Animator Sub-State Machines**.

### Base State Machine

The base state machine is simply an in-between for all of the Sub-State Machines.

![image-20240407-202814.png](../docutils/attachments//6357001/8224776.png?width=506)

### Grounded Mobile Sub-State Machine

The grounded sub-state machine drives grounded movement, such as idle, walking, running, etc.

![image-20240407-202932.png](../docutils/attachments//6357001/7929879.png?width=507)

### Grounded Immobile Sub-State Machine

The grounded immobile sub-state machine drives grounded movement, especially when the control of the payer is limited in some fashion.

![image-20240407-203014.png](../docutils/attachments//6357001/8224783.png?width=506)

### Aquatic Sub-State Machine

The aquatic sub-state machine drives aquatic movement such as swimming and diving.

![image-20240407-203045.png](../docutils/attachments//6357001/7929887.png?width=506)

### Airborne Sub-State Machine

The airborne sub-state machine drives non-grounded movement, such as jumping and falling.

![image-20240407-203123.png](../docutils/attachments//6357001/7929893.png?width=506)

### Scaling Sub-State Machine

The scaling sub-state machine drives climbing movement.

![image-20240407-203200.png](../docutils/attachments//6357001/7995439.png?width=506)

Updating Animator Transitions
=============================

### Summary

**Animator** transitions can be manipulated to suit your needs to reflect transitions that are more suitable for you and your character. The available parameters are detailed further in [Unity’s Animator documentation](https://docs.unity3d.com/Manual/class-Animator.md). For more information on how to integrate new **Animator** transitions into Character Controller Plus, please view the [Creating Custom States](Creating-Custom-States_10813474.md) section.

![image-20240416-235618.png](../docutils/attachments//6357001/10846216.png?width=760)

Updating Animator Parameters
============================

### Introduction

**Animator** parameters may be updated, whether it be by changing the names of **Animator** parameters, adding them and/or removing them. When manipulating **Animator** parameters, it is imperative that the names of the changed **Animator** parameters are also reflected in the Character Controller Plus code base.

### Updating Parameters

To reflect the changes made to any **Animator** parameters, developers can dive into the code base and navigate to the `PlayerAnimationMap.cs` class, located at `../Character Controller Plus/Demo Character/Scripts/State Manager/State Manager Parameter Store` directory, relative to the project root.

![image-20240416-231944.png](../docutils/attachments//6357001/10813459.png?width=760)

Here you can find all of the **Animator** parameters which are assigned to static variables as to provide easily accessible data to relative state modules.

To reflect any changes, additions or deletions to your **Animator** parameters, simply add, remove or update the parameter that is targeting the state at which you aim to change. Additional parameters may be added if the developer so chooses to create additional custom states. For more information on how to integrate new **Animator** parameters into Character Controller Plus, please view the [Creating Custom States](Creating-Custom-States_10813474.md) section.