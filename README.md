# Unity_Attributes
Unity Attributes for Better Inspector Experience

1. SerializeField
2. HideInInspector
3. Header
4. Space
5. Tooltip
6. Range
7. TextArea
8. HelpURL
9. RequireComponent
10. ContextMenuItem
11. ContextMenu


<h3> Hello! Let's build on the following simple Unity script and improve the inspector experience for it by adding in attributes. </h3> 

```

using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    private float damageDealt = 5;
    private int currentHealth = 50;
    public int maxHealth = 100;
    private string characterName = "Unity";
    private string characterDescription = "Unity Attributes";
}

```

In the inspector view, it looks like this:

![inspector view](https://github.com/PrathamArtz/Unity_Attributes/raw/main/Images/Inspector%20View.jfif)

Note that only the public field maxHealth shows up on the inspector. All the private variables are hidden

<br />
<h2> SerializeField</h2> 

To expose private variables in the inspector so that you could change it, simply add the SerializeField attribute.


```

using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    [SerializeField] private float damageDealt = 5;
    [SerializeField] private int currentHealth = 50;
    public int maxHealth = 100;
    [SerializeField] private string characterName = "Unity";
    [SerializeField] private string characterDescription = "Unity Attributes";
}

```
![SerializeField view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Images/SerializeField.jfif)

Inspector view with SerializeField addition

<h2>HideInInspector</h2>
To do the opposite and hide public variables from the inspector, simply add the HideInInspector attribute.

<br><br />

```
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    [SerializeField] private float damageDealt = 5;
    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;
    [SerializeField] private string characterName = "Unity";
    [SerializeField] private string characterDescription = "Unity Attributes";
}
```
![HideInInspector view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Images/HideInInspector.jfif)

Inspector view with HideInInspector addition

<h2>Header</h2>
Now, let's organize things a bit by adding in labels above the variables in the inspector by using the Header attribute.

```
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] private float damageDealt = 5;
    
    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";
    [SerializeField] private string characterDescription = "Unity Attributes";
}
```
![Header view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Images/Header.jfif)

Inspector view with Header addition

<h2>Space</h2>
To further group variables in the inspector, let's also add in a space between the health and damage stats using the Space attribute.

```
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] private float damageDealt = 5;

    [Space(20)]

    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";
    [SerializeField] private string characterDescription = "Unity Attributes";
}
```
![Space view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Images/Space.jfif)

Inspector view with Space addition

<h2>Tooltip</h2>
Variable naming is difficult and sometimes variables just need more context. To help with this, we can use the Tooltip attribute so that when you hover over a variable in the inspector, more context about it shows.

```
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] 
    [Tooltip("The damage dealt by the character")]
    private float damageDealt = 5;

    [Space(20)]

    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";
    [SerializeField] private string characterDescription = "Unity Attributes";
}

```
![Tooltip view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Gif/Tooltip.gif)

Inspector Tooltip demo

<h2>Range</h2>
Aside from putting in raw numeric values in the inspector, we can also use the Range attribute to provide us a slider, which gives us more control over the input and prevent invalid values.

```
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] 
    [Tooltip("The damage dealt by the character")]
    [Range(0f, 5f)]
    private float damageDealt = 5;

    [Space(20)]
    
    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";
    [SerializeField] private string characterDescription = "Unity Attributes";
}
```

![Range view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Gif/Range.gif)

Inspector Tooltip demo

<h2>TextArea</h2>
With the string variables, we can do much better as well by providing a larger text area in the inspector, making it easier to edit and manage longer text content.

```
using UnityEngine;

public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] 
    [Tooltip("The damage dealt by the character")]
    [Range(0f, 5f)]
    private float damageDealt = 5;

    [Space(20)]

    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";

    [SerializeField] 
    [TextArea]
    private string characterDescription= "Unity Attributes";
}
```
![TextArea view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Gif/TextArea.gif)

Inspector TextArea view

<h2>HelpURL</h2>
This next attribute, the HelpURL, is useful in team projects. With it, you make it easier to access documentation through a link you provide.

```
using UnityEngine;

[HelpURL("https://www.renz.is/useful-unity-attributes-for-better-inspector-experience/")]
public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] 
    [Tooltip("The damage dealt by the character")]
    [Range(0f, 5f)]
    private float damageDealt = 5;

    [Space(20)]

    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";

    [SerializeField] 
    [TextArea]
    private string characterDescription= "Unity Attributes";
}
```
![HelpURL view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Images/HelpURL.jfif)

Clicking the question mark at the top right of the attached script component (outlined by a red box) will bring the user to the link you provided

<h2>RequireComponent</h2>
Now, when a script is going to be using a specific component, the RequireComponent attribute is helpful in making sure that this specific component is assigned to the gameobject. Not only that, but it also won't allow the component to be removed from the object.

```
using UnityEngine;

[HelpURL("https://docs.unity.com/ScriptReference/Rigidbody.html")]
[RequireComponent(typeof(Rigidbody))]
public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] 
    [Tooltip("The damage dealt by the character")]
    [Range(0f, 5f)]
    private float damageDealt = 5;

    [Space(20)]

    [SerializeField] private int currentHealth = 50;
    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";

    [SerializeField] 
    [TextArea]
    private string characterDescription= "Unity Attributes";
}
```
![RequireComponent view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Images/RequireComponent.jfif)

Rigidbody component has been attached automatically to the gameobject

![RequireComponent view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Gif/RequireComponent.gif)

RequireComponent attribute demo preventing the removal of the specified required component

<h2>ContextMenuItem</h2>

By adding the ContextMenuItem attribute in a variable, you will be able to right click this variable in the inspector and run a function you specify.

```
using UnityEngine;

[HelpURL("https://docs.unity.com/ScriptReference/Rigidbody.html")]
[RequireComponent(typeof(Rigidbody))]
public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] 
    [Tooltip("The damage dealt by the character")]
    [Range(0f, 5f)]
    private float damageDealt = 5;

    [Space(20)]

    [SerializeField] 
    [ContextMenuItem("Reset current health", "ResetCurrentHealth")]
    private int currentHealth = 50;

    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";

    [SerializeField] 
    [TextArea]
    private string characterDescription= "Unity Attributes";

    private void ResetCurrentHealth()
    {
        currentHealth = 100;
    }
}
```
![ContextMenuItem view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Gif/ContextMenuItem.gif)

Inspector ContextMenuItem demo

<h2>ContextMenu</h2>

To conclude, the ContextMenu works the same way as the ContextMenuItem. It provides you access to run a function you again specify when you right click the script component in the inspector.

```
using UnityEngine;

[HelpURL("https://docs.unity.com/ScriptReference/Rigidbody.html")]
[RequireComponent(typeof(Rigidbody))]
public class ExampleScript : MonoBehaviour
{
    [Header("Character Stats")]
    [SerializeField] 
    [Tooltip("The damage dealt by the character")]
    [Range(0f, 5f)]
    private float damageDealt = 5;

    [Space(20)]

    [SerializeField] 
    [ContextMenuItem("Reset current health", "ResetCurrentHealth")]
    private int currentHealth = 50;

    [HideInInspector] public int maxHealth = 100;

    [Header("Character Description")]
    [SerializeField] private string characterName = "Unity";

    [SerializeField] 
    [TextArea]
    private string characterDescription= "Unity Attributes";

    private void ResetCurrentHealth()
    {
        currentHealth = 100;
    }

    [ContextMenu("Goodbye")]
    private void Goodbye()
    {
        Debug.Log("Goodbye now! Hope it helped.");
    }
}
```

![ContextMenu view](https://github.com/PrathamArtz/Unity_Attributes/blob/main/Gif/ContextMenu.gif)

ContextMenu inspector demo
