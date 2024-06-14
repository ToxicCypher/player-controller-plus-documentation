*   [Overview](#LegInverseKinematics(IK)-Overview)
    *   [Provided Feature](#LegInverseKinematics(IK)-ProvidedFeature)
*   [Leg IK Parameters](#LegInverseKinematics(IK)-LegIKParameters)
*   [Hierarchical Requirements](#LegInverseKinematics(IK)-HierarchicalRequirements)
*   [Game Objects & Components](#LegInverseKinematics(IK)-GameObjects&Components)
    *   [Character Root Components](#LegInverseKinematics(IK)-CharacterRootComponents)
        *   [Rig Builder](#LegInverseKinematics(IK)-RigBuilder)
        *   [Animation Event IK Handler](#LegInverseKinematics(IK)-AnimationEventIKHandler)
        *   [Bone Renderer \[Optional\]](#LegInverseKinematics(IK)-BoneRenderer[Optional])
    *   [Nested Game Objects](#LegInverseKinematics(IK)-NestedGameObjects)
        *   [Leg Rig](#LegInverseKinematics(IK)-LegRig)
        *   [Left | Right Leg](#LegInverseKinematics(IK)-Left|RightLeg)
        *   [Left | Right Leg Target](#LegInverseKinematics(IK)-Left|RightLegTarget)
        *   [Left | Right Leg Hint](#LegInverseKinematics(IK)-Left|RightLegHint)
        *   [Left | Right Controller](#LegInverseKinematics(IK)-Left|RightController)

Overview
========

### Provided Feature

The Leg IK rig allows the player to detect surfaces as the player is grounded. The players leg will bend at the knee and adjust to the surface that is being walked on in order to provide a level of continuity within your project and to make traversing slopes look much more realistic.

Leg IK is highly configurable and many adjustments can be made to suit the needs of your character to provide the level of inverse kinematics that best suits your project needs. Please see the Leg IK Parameters section for more information regarding the available configuration.

For quick use of the Leg IK system, players can find a Leg IK prefab which can be applied to any Humanoid character that they choose. Using the curated Leg IK prefab and following guide lines in this documentation will get your Leg IK system setup quickly.

Leg IK Parameters
=================

_Tooltips are provided for all of the available configuration within the Unity Editor._

<table data-table-width="1000" data-layout="default" data-local-id="74a96b6f-6289-4dc9-be63-7bfa8f0e9f4f" class="confluenceTable"><colgroup><col style="width: 175.0px;"><col style="width: 339.0px;"><col style="width: 486.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Parameter</strong></p></th><th class="confluenceTh"><p><strong>Header</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>Foot Two Bone IK</p></td><td class="confluenceTd"><p>IK Components</p></td><td class="confluenceTd"><p>The Two Bone IK Constraint attached to the relevant leg.</p></td></tr><tr><td class="confluenceTd"><p>Target</p></td><td class="confluenceTd"><p>IK Components</p></td><td class="confluenceTd"><p>A reference to the &lt;Lateral&gt; Leg_target object for the relevant leg.</p></td></tr><tr><td class="confluenceTd"><p>Foot Bone</p></td><td class="confluenceTd"><p>IK Components</p></td><td class="confluenceTd"><p>A reference to the foot bone in your character rig for the relevant leg. This should be the same value as the value used in the Tip parameter of the Two Bone IK Constraint component.</p></td></tr><tr><td class="confluenceTd"><p>Origin</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>The origin of the raycast, the origin provided is relative to the position of the Game Object this script is attached to.</p></td></tr><tr><td class="confluenceTd"><p>Layers</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>Objects within the selected layers can be used to detect IK positioning.</p></td></tr><tr><td class="confluenceTd"><p>Distance</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>Distance from the player that can detect surfaces within the allowed layers.</p></td></tr><tr><td class="confluenceTd"><p>Y Scale</p></td><td class="confluenceTd"><p>Raycast Components</p></td><td class="confluenceTd"><p>Scaled the Raycasts hit point up by the specified factor. This value can be used to raise feet off of hit points to account for varying feet sizes, shapes, types.</p></td></tr><tr><td class="confluenceTd"><p>Apply IK In States</p></td><td class="confluenceTd"><p>IK Settings</p></td><td class="confluenceTd"><p>The states that IK will be performed on this constraint.</p></td></tr><tr><td class="confluenceTd"><p>Positioning Speed</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The speed at which IK targeting occurs.</p></td></tr><tr><td class="confluenceTd"><p>Depositioning Speed</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The speed at which IK targeting is dissolved.</p></td></tr><tr><td class="confluenceTd"><p>Initial Weight</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The starting weight of the IK rig.</p></td></tr><tr><td class="confluenceTd"><p>Target Weight</p></td><td class="confluenceTd"><p>IK Properties</p></td><td class="confluenceTd"><p>The target weight of the IK rig when a surface that can be used for IK is detected.</p></td></tr><tr><td class="confluenceTd"><p>Debug</p></td><td class="confluenceTd"><p>Debug Settings</p></td><td class="confluenceTd"><p>Flags debug mode.</p></td></tr></tbody></table>

Hierarchical Requirements
=========================

The Animation Rigging package from Unity requires that the Rig components be nested under the same parent as the Rig game object, see image below.

![image-20240417-004617.png](../docutils/attachments//3112962/10715188.png?width=443)

Game Objects & Components
=========================

### Character Root Components

#### Rig Builder

The **Rig Builder** object is a component added to the root Game Object which is used to define which Rig Layers are active. In-order for Leg IK to function, the Leg Rig Game Object must be supplied to the list of Rig Layers.

#### Animation Event IK Handler

The Animation Event IK Handler script is needed to consume animation events which are triggered during selected key frames in targeted animation clips. The events that are fired off during the lifecycle of an animation clip are used to enable/disable Leg IK rigs by smoothing the IK weights, either up or down depending on the animation event that was fired. There are currently two events at your disposal.

<table data-table-width="760" data-layout="default" data-local-id="434b5f0c-3273-43c2-add9-cfa139858cc4" class="confluenceTable"><colgroup><col style="width: 135.0px;"><col style="width: 239.0px;"><col style="width: 386.0px;"></colgroup><tbody><tr><th class="confluenceTh"><p><strong>Event Name</strong></p></th><th class="confluenceTh"><p><strong>Available Event Parameters</strong></p></th><th class="confluenceTh"><p><strong>Details</strong></p></th></tr><tr><td class="confluenceTd"><p>IKActive</p></td><td class="confluenceTd"><p>“Left” or “Right”</p></td><td class="confluenceTd"><p>Enables IK on the left or right leg.</p></td></tr><tr><td class="confluenceTd"><p>IKInactive</p></td><td class="confluenceTd"><p>“Left” or “Right”</p></td><td class="confluenceTd"><p>Disables IK on the left or right leg.</p></td></tr></tbody></table>

Each of the mentioned events must be passed a string which tell the Animation Event IK Handler script which legs IK should be active or inactive. If “Left” or “Right” string parameters are not provided, a console warning will be displayed.

All other event parameters are ignored.

![image-20240417-005104.png](../docutils/attachments//3112962/10551322.png?width=760)

#### Bone Renderer \[Optional\]

The **Bone Renderer** component is used to display the character Rig, which allows for Rig components to become selectable within the Scene view.

![image-20240417-003548.png](../docutils/attachments//3112962/10813498.png?width=760)

### Nested Game Objects

#### Leg Rig

Leg Rig is the root component for the Leg IK system. There is little to no significance here besides the fact that this Game Object is the parent to the remaining Leg IK Game Objects. The Rig component attached to this Game Object should remain at a weight of 1 as this value is not manipulated in any way by the Leg IK system and changing the value may result in poor IK results.

#### Left | Right Leg

Each legs remaining components are divided into two sections, one for the left leg and another for the right leg. This component contains a Two Bone IK Constraint component which has already been prepared for the current Rig. The Tip, Mid and Root parameters will need to be updated if/when the Rig is ever changed.

If the Rig is changed, you can quickly configure the Two Bone IK Constraint component by providing a value for the Tip parameter, right clicking on the header of the Two Bone IK Constraint component and selecting the “Auto Setup from Tip Transform option”. Doing this will automatically fill in the remaining bone transforms.

![image-20240417-010236.png](../docutils/attachments//3112962/10813522.png?width=499)

#### Left | Right Leg Target

The leg target is used to tell the player Rig where to place it’s foot. Adjust the location of this game object to sit within the laterally correct ankle. Users can match the rotation of the Tip (foot) bone by first selecting the target, then the foot bone, then in the Animation Rigging menu, select the Align Rotation option.

While in play mode, the target will be continuously adjusting its position based on the location of the foot bone, assuming Leg IK is in an active state.

![image-20240417-011325.png](../docutils/attachments//3112962/10485835.png?width=760)

#### Left | Right Leg Hint

The leg hint is simply used to help guide the direction that the knee should move towards when the legs are bending as a result of Leg IK activity. The hint object should be placed approximately 0.5 units in the direction of the players forward.

![image-20240417-011452.png](../docutils/attachments//3112962/10780742.png?width=319)

#### Left | Right Controller

Depending on the lateral side the leg is on, there is a Right Foot IK Controller component and a Left Foot IK Controller component. Both scripts behave in the same fashion and supply the same functionality but the target leg differs.

The Controller object is what drives the core functionality of the Leg IK system. The controller should be positioned slightly above the ground, near the characters ankle. This object contains a script which houses the configuration for how users would like the Leg IK system to behave. For more information regarding these parameters, please see the Leg IK Parameters section.

![image-20240417-012229.png](../docutils/attachments//3112962/10485845.png?width=491)