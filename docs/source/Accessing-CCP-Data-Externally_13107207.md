/\*<!\[CDATA\[\*/ div.rbtoc1718320129278 {padding: 0px;} div.rbtoc1718320129278 ul {list-style: none;margin-left: 0px;} div.rbtoc1718320129278 li {margin-left: 0px;padding-left: 0px;} /\*\]\]>\*/

*   [Overview](#AccessingCCPDataExternally-Overview)
*   [How To](#AccessingCCPDataExternally-HowTo)

Overview
========

This document provides information on how developers can access Character Controller Plus information externally through their own scripts. This feature is important as it provides a layer of transparency and can be used to drive events suitable to your project needs.

How To
======

To access Character Controller Plus data externally through script, developers can use the following syntax.

_In this example, we are getting the current state of the player._

```
using CCP;
using UnityEngine;

public class MyScript
{
    public void MyFunction()
    {      
        /* Check the current state */
        if (Meta.GetState() == PlayerState.Idle)
        {
            /* Perform actions based on your conditions */
            Meta.Get().movement = Vector3.zero;
            
            /* Pull data for downstream use */
            Vector3 direction = Meta.Get().direction;
        }
    }
}
```

Character Controller Plus data is easily accessible through the no frills **Meta** class. This class is bare bones, exposing all available parameters with the **Get**() functions and a simplified **GetState**() function which returns PlayerState types related to the current state. Extend functionality as needed.

```
namespace CCP
{
	/*
	 This state is used as a conduit for current state information access.
	 */

	public class Meta
	{
        public static CharacterControllerPlus Get()
		{
			return CharacterControllerPlus.Instance;
		}

        public static PlayerState GetState()
        {
            return CharacterControllerPlus.Instance.DetermineState(CharacterControllerPlus.Instance.currentState);
        }
    }
}
```