# ScriptableObject as Events

If you follow most examples, you end up using UnityEvent which means you have to wire up event listeners in the editor and make class methods public. I found this to be hard to manage and keep up with at scale even in medium projects.&#x20;

Instead, here is a solution that takes advantage of using ScriptableObjects to define events and keep them organized in your project.&#x20;

This solution uses C# Actions for event publisher and subscribing in code. It's simple, performant and results in clean code.&#x20;

```
    public class GameEvent<T> : ScriptableObject
    {
        [Header("Debugging")]

        [SerializeField] private bool enableDebug;
        [SerializeField] private Color color = Color.white;

        public event Action<T> OnEvent;

        public void Raise(GameObject caller, T arg)
        {
            if (enableDebug)
            {
                Debug.LogFormat(this, "<color=#{3}>Event: {0}, Caller: {1}, Arg: {2}</color>", name, caller.name, arg.ToString(), ColorUtility.ToHtmlStringRGB(color));
            }

            OnEvent?.Invoke(arg);
        }

    }
```

To implement a typed event simply create new scripts for the types to be available in the editor menu.

```
    [CreateAssetMenu(fileName = "GameEvent", menuName = "Events/BoolGameEvent")]
    public class BoolGameEvent : GameEvent<bool>
    {
    }
```

You can then create events from the menu as assets in your project and add them as fields in MonoBehaviors.&#x20;

```
public class Example: MonoBehaviour
    {

        [Header("Published Events")]
        [SerializeField] private IntGameEvent counterEvent;
   
        [Header("Subscribed Events")]
        [SerializeField] private BoolGameEvent alertEvent;

        private void OnEnable()
        {
            if (alertEvent) alertEvent.OnEvent += OnAlert;
        }

        private void OnDisable()
        {
            if (alertEvent) alertEvent.OnEvent -= OnAlert;
        }

        private void OnAlert(bool enabled)
        {
          // do something
        }

         public void CountStuff()
         {
             counterEvent.Raise(1);
         }
    }
```
