# Simple Follow Camera

To make a simple follow camera, create a script attached to the camera with:

```

using UnityEngine;

public class FollowCamera : MonoBehaviour
{
    
    [SerializeField][Tooltip("Set the target game object to follow.")] 
    GameObject target;
    
    [SerializeField][Tooltip("Set the distance the camera should offset from the target position.")] 
    Vector3 offset = new Vector3(0,0,-10);
    
    void LateUpdate()
    {
        transform.position = target.transform.position + offset;
    }
}
```

* To improve use lerping to smooth movement
* Cinemachine has advanced follow features
