# Changing Burst at Runtime

With Unity 2020+ particle system you can change the properties of one or more bursts in the Emissions module. Setting this value is not intuitive:

```
public class Effect: MonoBehaviour
{
    private ParticleSystem _particles;
    private ParticleSystem.Burst _burst;

    private void Awake()
    {
        _particles = GetComponent<ParticleSystem>();
        _burst = _particles.emission.GetBurst(0);
    }

    public void Emit(int score)
    {
        _burst.count = score;
        _particles.emission.SetBurst(0, _burst);
        _particles.Play();
    }

}
```
