# 2D Rigidbody Types

To add physics to a 2D game object, add a RigidBody2D component and a Collider2D for collisions.

* Adding a Rigidbody means that the physics engine is controlling the transform now, if you directly try to control the transform this can cause problems and unpredictable behavior
* Attached colliders won't collide with each other and will be moved by the RigidBody

## Body Types

The options contols movement behavior and collider interaction

### Dynamic

This is the default and most common type, used for the most interactivity.

* designed to move under simulation
* collides with all other types
* movement controlled by velocity, gravity and collisions
* apply forces via the API to move

### Kinematic:

Also used to move under simulation, without gravity effects.

* has inifinite mass
* only collides with Dynamic rigid bodies

### Static:

Does not move, acts as an immovable object and only collides with Dynamic rigid bodies.

* same as having a collider without a rigidbody component
* static and kinematic colliders will react if one is a trigger

## Properties

* enable and disable physics with the 'Simulated' property
* 'Linear Drag' for movement
* 'Angular Drag' for rotation
* Collision Detection
*
  * Discrete: means colliders can oberlap or pass through if moving fast enough
*
  * Continuous: cannot overlap / pass thru, more CPU intensive
* Use 'Interpolate' to smooth jerky movement
