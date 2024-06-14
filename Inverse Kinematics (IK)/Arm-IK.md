*   [Overview](#Hand&ArmInverseKinematics(IK)-Overview)
    *   [Limitations](#Hand&ArmInverseKinematics(IK)-Limitations)
    *   [Provided Feature](#Hand&ArmInverseKinematics(IK)-ProvidedFeature)
*   [Hand & Arm IK Parameters](#Hand&ArmInverseKinematics(IK)-Hand&ArmIKParameters)
*   [Hierarchical Requirements](#Hand&ArmInverseKinematics(IK)-HierarchicalRequirements)
*   [Game Objects & Components](#Hand&ArmInverseKinematics(IK)-GameObjects&Components)
    *   [Character Root Components](#Hand&ArmInverseKinematics(IK)-CharacterRootComponents)
        *   [Rig Builder](#Hand&ArmInverseKinematics(IK)-RigBuilder)
        *   [Bone Renderer \[Optional\]](#Hand&ArmInverseKinematics(IK)-BoneRenderer[Optional])
    *   [Nested Game Objects](#Hand&ArmInverseKinematics(IK)-NestedGameObjects)
        *   [Arm Rig](#Hand&ArmInverseKinematics(IK)-ArmRig)
        *   [Left | Right Arm](#Hand&ArmInverseKinematics(IK)-Left|RightArm)
        *   [Left | Right Arm Target](#Hand&ArmInverseKinematics(IK)-Left|RightArmTarget)
        *   [Left | Right Arm Hint](#Hand&ArmInverseKinematics(IK)-Left|RightArmHint)
        *   [Left | Right Controller](#Hand&ArmInverseKinematics(IK)-Left|RightController)

Overview
========

### Limitations

The Rig provided in the Character Controller Plus package does not adhere to the Rig requirements needed for Hand & Arm IK to work properly.

Hand & Arm IK is a preview process as this feature contains limitations that may deem this feature not suitable to the nature of your Rig. That being said, use this feature with caution as unintended results are expected.

While under development, I have found that using **Mixamo** generated Rigs are suitable for use of the Hand & Arm IK feature, possible to the nature of the Rig and its bone rotation.

### Provided Feature

This feature is particularly designed for states such as Idle, Walking, Running, Crouching and Crouch Walking.

The Hand & Arm IK rig allows the player to detect surfaces as the player nears them. The player will reach their hand towards the location of the detected surface while rotating the hand towards the surface of the detected object.

Hand IK is highly configurable and many adjustments can be made to suit the needs of your character to provide the level of inverse kinematics that best suits your project needs. Please see the Hand & Arm IK Parameters section for more information regarding the available configuration.

Hand & Arm IK Parameters
========================

<table data-table-width="1011" data-layout="default" data-local-id="082d92b5-ad0e-4747-995e-0eda89df58fe" class="confluenceTable"><colgroup><col style="width: 177.0px;"><col style="width: 205.0px;"><col style="width: 626.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Hand Two Bone IK</p></td><td class="confluenceTd"><p>IK Components</p></td><td class="confluenceTd"><p>The Two Bone IK Constraint component attached to the relevant arm.</p></td></tr><tr><td class="confluenceTd"><p>Hand Multi Rotation</p></td><td class="confluenceTd"><p>IK Components</p></td><td class="confluenceTd"><p>The Multi Rotation Constraint component attached to the relevant arm.</p></td></tr><tr><td class="confluenceTd"><p>Target</p></td><td class="confluenceTd"><p>IK Components</p></td><td class="confluenceTd"><p>A reference to the &lt;Lateral&gt; Arm_target object for the relevant arm.</p></td></tr><tr><td class="confluenceTd"><p>Origins</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>A list of raycast origins, the origin provided is relative to the position of the Game Object this script is attached to. (This list length must be equal to the directions list length)</p></td></tr><tr><td class="confluenceTd"><p>Directions</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>A list of raycast direction. (This list length must be equal to the origins list length)</p></td></tr><tr><td class="confluenceTd"><p>Layers</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>Objects within the selected layers can be used to detect IK positioning.</p></td></tr><tr><td class="confluenceTd"><p>Distance</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>Scaled distance from the player that can detect surfaces within the allowed layers.</p></td></tr><tr><td class="confluenceTd"><p>Y Scale</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>Scales the Raycasts hit point up by the specified factor. This value can be used to raise hands off of hit points to account for varying hand sizes, shapes, types.</p></td></tr><tr><td class="confluenceTd"><p>Apply IK In States</p></td><td class="confluenceTd"><p>IK Settings</p></td><td class="confluenceTd"><p>The states that IK will be performed on this constraint.</p></td></tr><tr><td class="confluenceTd"><p>Hand Rotation Speed</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The speed at which the IK target is rotated.</p></td></tr><tr><td class="confluenceTd"><p>Positioning Speed</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The speed at which IK targeting occurs.</p></td></tr><tr><td class="confluenceTd"><p>Depositioning Speed</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The speed at which IK targeting is dissolved.</p></td></tr><tr><td class="confluenceTd"><p>Initial Weight</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The starting weight of the IK rig.</p></td></tr><tr><td class="confluenceTd"><p>Target Weight</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The target weight of the IK rig when a surface that can be used for IK is detected.</p></td></tr><tr><td class="confluenceTd"><p>Debug</p></td><td class="confluenceTd"><p>Debug Settings</p></td><td class="confluenceTd"><p>Flags debug mode, showing raycasts in the game view.</p></td></tr></tbody></table>

Hierarchical Requirements
=========================

The Animation Rigging package from Unity requires that the Rig components be nested under the same parent as the Rig game object, see image below.

![image-20240418-011216.png](../docutils/attachments//3211266/11730946.png?width=443)

Game Objects & Components
=========================

### Character Root Components

#### Rig Builder

The **Rig Builder** object is a component added to the root Game Object which is used to define which Rig Layers are active. In-order for Arm IK to function, the Arm Rig Game Object must be supplied to the list of Rig Layers.

#### Bone Renderer \[Optional\]

The **Bone Renderer** component is used to display the character Rig, which allows for Rig components to become selectable within the Scene view.

![image-20240417-003548.png](../docutils/attachments//3211266/11403310.png?width=760)

### Nested Game Objects

#### Arm Rig

Arm Rig is the root component for the Hand & Arm IK system. There is little to no significance here besides the fact that this Game Object is the parent to the remaining Hand & Arm IK Game Objects. The Rig component attached to this Game Object should remain at a weight of 1 as this value is not manipulated in any way by the Hand & Arm IK system and changing the value may result in degraded IK results.

#### Left | Right Arm

Each arms remaining components are divided into two sections, one for the left arm and another for the right arm. This component contains a Two Bone IK Constraint component which has already been prepared for the current Rig. The Tip, Mid and Root parameters will need to be updated if/when the Rig is ever changed.

If the Rig is changed, you can quickly configure the Two Bone IK Constraint component by providing a value for the Tip parameter, right clicking on the header of the Two Bone IK Constraint component and selecting the “Auto Setup from Tip Transform option”. Doing this will automatically fill in the remaining bone transforms.

![image-20240418-004852.png](../docutils/attachments//3211266/11501613.png?width=493)

This component also contains a Multi-Rotation Constraint which is responsible for handling the rotation of the source object or in this case, the Left | Right Arm\_target.

![image-20240418-005115.png](../docutils/attachments//3211266/11534369.png?width=493)

#### Left | Right Arm Target

The arm target is used to tell the player Rig where to place it’s hand. Adjust the location of this game object to sit within the reach of the arms of the character. The decided position will dictate the location and distance that the player will reach their hands out to.

![image-20240418-005526.png](../docutils/attachments//3211266/11534376.png?width=760)

#### Left | Right Arm Hint

The arm hint is simply used to help guide the direction that the elbows should move towards when the arms are bending as a result of Arm IK activity.

![image-20240418-010348.png](../docutils/attachments//3211266/11239454.png?width=760)

#### Left | Right Controller

The Controller object is what drives the core functionality of the Hand & Arm IK system. The controller should be positioned under the bicep and to the side of the peck.

The positioning of the Controller Game Object is crucial to the accuracy of your Hand & Arm IK setup. This is due to the fact that the raycasts that detect when Hand & Arm IK should be active, originate from this object. The number of raycasts, origins of raycasts and directions of raycasts can be manipulated directly from the Hand IK Controller component by providing equal parts Origins and Directions vectors.

![image-20240418-010955.png](../docutils/attachments//3211266/11305006.png?width=496)

This object contains a script which houses the configuration for how users would like the Arm IK system to behave. For more information regarding these parameters, please see the Arm IK Parameters section.

![image-20240418-010703.png](../docutils/attachments//3211266/11239460.png?width=730)

![image-20240418-010502.png](../docutils/attachments//3211266/11534383.png?width=493)