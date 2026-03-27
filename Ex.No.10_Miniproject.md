# Ex.No: 10  Implementation of 3D Game – Penalty Kick Game

### DATE: 23-03-2026
### REGISTER NUMBER: 212223043005

## AIM:
To develop a **3D Penalty Kick Game** in Unity using physics and simple AI strategy.


## Algorithm:
1. Open Unity Hub and create a new 3D project  
2. Create a Plane to act as the ground  
3. Add a Sphere as the football  
4. Apply Rigidbody to the ball for physics movement  
5. Create a Goal Post using 3D cubes  
6. Add a Goal Trigger using Box Collider (Is Trigger enabled)  
7. Create a Goalkeeper object (cube or 3D model)  
8. Add movement script to goalkeeper  
9. Write script to kick the ball using keyboard input  
10. Detect goal using OnTriggerEnter()  
11. Display result (Goal / Miss)  
12. Run and test the game  

---

## Program:

### BallController.cs
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

### GoalTrigger.cs
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

### GoalKeeper.cs
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

---

## Output:

## before kick
<img width="1919" height="1023" alt="Screenshot 2026-03-27 134830" src="https://github.com/user-attachments/assets/736adf01-0f3e-4cfe-b6d4-3c5d338fc780" />

## After kick
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4f66bf99-0d0a-4d10-821e-8c6530be8b66" />

## Result:

Thus, the **3D Penalty Kick Game** was successfully developed using Unity and adopted **basic AI technology**.
