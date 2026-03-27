# Ex.No: 10 -Implementation of 3D Game (Penalty Kick Game)
### DATE: 23/03/2026                                                                          
### REGISTER NUMBER : 212223043005
### AIM:

To develop a 3D Penalty Kick Game in Unity using basic physics and simple AI strategy for the goalkeeper.
### Algorithm:
1. Create a new 3D Unity Project
2. Add a Plane as the football ground
3.Create a Ball (Sphere) and apply Rigidbody for physics
4.Create a Goal Post using cubes
5.Add a Goal Net area (Trigger Box Collider)
6.Create a Goalkeeper (Cube / Human Model)
7.Add movement script to control goalkeeper (AI or manual)
8.Apply force to the ball when player kicks (mouse click / key input)
9.Detect goal using OnTriggerEnter() method
10.Display result (Goal / Miss)
11.Restrict ball movement inside goal using colliders
12.Run the scene and test gameplay
### Program:
### Ball Kick Script (BallController.cs)
```
using UnityEngine;

public class BallController : MonoBehaviour
{
    public Rigidbody rb;
    public float kickForce = 500f;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            rb.AddForce(new Vector3(0, 200, 500));
        }
    }
}
```
### Goal Detection Script (GoalTrigger.cs)
```
using UnityEngine;

public class GoalTrigger : MonoBehaviour
{
    private void OnTriggerEnter(Collider other)
    {
        if (other.CompareTag("Ball"))
        {
            Debug.Log("GOAL!!!");
        }
    }
}
```
### Goalkeeper Movement Script (GoalKeeper.cs)
```
using UnityEngine;

public class GoalKeeper : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float move = Mathf.Sin(Time.time) * speed;
        transform.position = new Vector3(move, transform.position.y, transform.position.z);
    }
}
```
### Output:


### Result:
Thus, the Penalty Kick Game was successfully developed using Unity and basic physics, and simple AI strategy was implemented for goalkeeper movement.
