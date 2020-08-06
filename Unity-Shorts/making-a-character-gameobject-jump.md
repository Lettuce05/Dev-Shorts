# Making a Character/GameObject Jump

In Unity you can use the physics engine to add force to a character or gameObject, for example making a character jump. This can be done using the AddForce method that belongs to the RigidBody Class. 

In order to add force to an object you must first create/get access to the game objects rigid body component. This can be done by creating a new rigid body object, as shown below.

```C#
/*Creating a Rigid body object that corresponds to your 
player/GameObject*/
private Rigidbody playerRb;
```
<br></br>

Next, to get access to the properties of your players rigid body, you must get the rigid body component and set the player rigid body to it. (This must be set in Unity's default Start method)

```C#
void Start()
{
	playerRb = GetComponent<Rigidbody>();
}
```
<br></br>
Now that you have access to your player's rigid body component, you can use the RigidBody.AddForce method. I will include basic documentation for the method at the bottom of this example/tutorial. In the example below we are adding a force on the y axis(aka. an upward force), making the character jump.

```C#
/*The AddForce method takes two arguments, the amount of force to apply on a specific axis, and the method in which the force is applied*/
playerRb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);

//Vector.up = y axis
//jumpForce = amount of Force
//ForceMode.Impulse = applies the force immediately
```
<br></br>
Thats all there is to adding force to an object in Unity, I hope this helped!

# Method Documentation

## RigidBody.AddForce

Function Definition:

```C#
public void AddForce(float x, float y, float z, ForceMode mode = ForceMode.Force);
```
<br></br>
The AddForce method takes three parameters for the direction and amount of force, and one parameter for the mode(how the force will be applied).

1.  x = amount of force applied in the direction of the x-axis(left or right)
2.  y = amount of force applied in the direction of the y-axis(up or down)
3.  z = amount of force applied in the direction of the z-axis
4.  (Optional) mode = how force will be applied, there is for options for this
    -   (Default) ForceMode.Force = Add a continuous force to the rigidbody, using its mass
    -   ForceMode.Acceleration = Add a continuous acceleration to the rigidbody, ignoring its mass
    -   ForceMode.Impulse = Add an instant force impulse to the rigidbody, using its mass
    -   ForceMode.VelocityChange = Add an instant velocity change to the rigidbody, ignoring its mass
<br></br>
Instead of giving distinct values for each axis, you can replace it with a Vector3 or Tranform method(to specify direction) and then multiply that method by the amount of force desired.

```C#
//Adds a upward force instantaneously
playerRb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
```
