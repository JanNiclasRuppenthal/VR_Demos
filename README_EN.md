[Deutsche Version](README_DE.md) | [English Version](README_EN.md)

---

# Locomotion and the Mall
**Entwickler:**
- Michael Feldmann 
- Philipp Geier
- Jan Niclas Ruppenthal

## Exercise Description
In this exercise, we were tasked with implementing a body-based and egocentric locomotion interface. This interface had to fit our chosen scenario or environment. We decided on a shopping mall as the environment, and the player moves through the building using a Segway to buy four requested items as quickly as possible.

---

## Task Part a)

### Locomotion Task
In this task, after a hard day at work, you receive a list of four different items you still need to buy. Unfortunately, there is only one department store that currently has them in stock. Since this store is scheduled for a renovation tomorrow, there is only one copy of each item available. 

Your goal is to collect all the required items. The four items are randomly selected at each start. It is guaranteed that you will have to collect exactly two items on both floors. Thus, you must ride the escalator at least once.

### Locomotion Used
* **Metaphor:** Steering-Leaning
    * *1 DOF vTranslation:* By leaning like a "Human Joystick" along the Z-axis.
    * *1 DOF vRotation:* By moving the controllers or the physical pole along the X-axis.
* **Travel Task:** Search
* **Functions:**
    * *Leaning (Translation):* Power function with a deadzone of 5 cm. Maximum speed: 5 meters per second after 34.8 cm.
    * *Steering (Rotation):* Power function with a deadzone of 10 cm. Maximum speed: 30 degrees per second after 28.3 cm.

### Testing the Task and Locomotion
*Conducted standing up by Michael Feldmann and Jan Niclas Ruppenthal*

Both testers were supposed to perform the task three times. However, both stopped after the second run because we noticed that our rotation causes cybersickness. To alleviate this slightly, we reduced the rotation speed from 45 degrees per second to 30 degrees per second. Additionally, the locomotion can be used while sitting down to prevent cybersickness, even though a Segway is normally operated standing up.

The translation via leaning was easy for both to use, and the task could be solved very quickly. On the escalator, locomotion is deactivated. Both testers liked this, as it served as a short resting period. Furthermore, the controllers vibrate while riding the escalator. When the vibration stops, it is an indicator to the user that locomotion is turned back on. Except for the escalator, we achieved a high degree of user freedom.

---

## Task Part b)

### Why was this interface implemented?
We looked for a familiar locomotion method that can be controlled with head and hand movements simultaneously. We also wanted to use something recognizable for immersion. Inspired by a Segway, the interface is therefore easier to learn.

### Strengths of the Interface
* **Multimodal Interaction:** The vibration of the controllers gets stronger or weaker depending on the Segway's speed. The physical pole can additionally amplify the controller vibration.
* **Immersion:** Since we chose a plausible scenario, we potentially achieve higher immersion.
* **Precision:** By using a power function for both translation and rotation, a higher precision of locomotion is achieved.
* **Deadzone:** We opted for a deadzone so that not every small movement of the head, controllers, or physical pole results in direct virtual movement.

### Weaknesses of the Interface
* A physical rotation of the entire body breaks the interface.
* Even though we reduced the rotation speed, it still sometimes causes cybersickness.
* Virtual vertical movement is only possible to a limited extent (only via the escalator). However, this is static, as locomotion is turned off there.
* Our method does not scale well to larger distances. We cannot simply increase the maximum speed for large distances, as the user would lose control of the Segway and cybersickness could increase.
* The virtual middle pole of the Segway causes a slight loss of immersion.
* The controllers must be tracked by the Quest 3. If tracking fails, the interface cannot be used.

### Measuring Performance and Usability
**Performance:**
* We can measure the required time for each participant.
* We log the number of collisions with walls or other objects. A high number of collisions indicates that the user could not perceive their surroundings well.

**Usability (Usability Study):**
* Participants perform the shopping task and must remember where they found the corresponding items.
* Usability can be evaluated after the task using standardized questionnaires like the System Usability Scale (SUS) or the NASA-TLX.
* This study can be expanded through a comparison: Our method could be compared with other interfaces, such as Pointing-based Steering or Redirected Walking.

---

## Starting the Project

When you open our Unity project, you may need to restart Unity several times.

Upon the first launch of the editor, a message may appear stating that changes in the `OVRPlugin` were detected. You just need to restart the editor. After the restart, three new error messages might appear:
> `[Package Manager Window] Error while getting auth code: User is not logged in or user status invalid. Unity.Editor.EditorApplication:Internal_CallUpdateFunctions ()`

In this case, simply restart Unity again; afterwards, the error messages should be gone. Alternatively, you can find proposed solutions [here in the Unity Forum](https://forum.unity.com/threads/package-manager-window-unable-to-perform-online-search.1136377/).

You can safely clear all remaining messages in the Unity Editor console. They have no effect on our application!

---

## Gameplay

The gameplay was inspired by the functionalities of a Segway.

**Movement:**
* **Forward:** Lean forward
* **Backward:** Lean backward
* **Turn right:** Move controllers (possibly with physical pole) along the positive X-axis
* **Turn left:** Move controllers (possibly with physical pole) along the negative X-axis

**Interactions:**
* **Collect items:** You can interact with the items directly using your hands.
* **Honk:** Press the `PrimaryHandTrigger` or `SecondaryHandTrigger`.
* **Toggle list:** Press the `PrimaryIndexTrigger` or `SecondaryIndexTrigger`.

---

## Assets

**SDKs:**
* [Meta XR Core SDK](https://assetstore.unity.com/packages/tools/integration/meta-xr-core-sdk-269169)
* [Meta Interaction OVR Integration SDK](https://assetstore.unity.com/packages/tools/integration/meta-xr-interaction-sdk-ovr-integration-265014) *(Note: We used the OVRCameraRigInteraction here, but deleted all pre-implemented interactions. This also installs the Meta XR Interaction SDK.)*
* Oculus XR Plugin

**Text:**
* TextMesh Pro

**Music and Sound:**
* [Background Music (Wii Shop)](https://www.101soundboards.com/sounds/24303004-wii-shop)
* [Horn/Honk](https://www.101soundboards.com/sounds/27481824-horn-honk-short)

**Department Store Models:**
* [Clock](https://assetstore.unity.com/packages/3d/props/interior/clock-free-44164)
* [Fountain](https://sketchfab.com/3d-models/fountain-1e2234e51a46400bbd3a71afd9c2b750#download)
* [Bench](https://assetstore.unity.com/packages/3d/environments/modern-bench-pack-221011)
* [Poster Frames](https://sketchfab.com/3d-models/poster-frame-fb500d75d785433c8b82fdafac9e18cb)
* [Pothos Plants](https://sketchfab.com/3d-models/free-pothos-potted-plant-money-plant-e9832f38484f4f85b3f9081b51fa3799)
* [Restroom Doors](https://assetstore.unity.com/packages/3d/props/interior/door-free-pack-aferar-148411)
* [Stores](https://sketchfab.com/3d-models/sketchfab-store-in-mall-957c1d65e6db4598a198f7ac3888fed1)

**Images for the Posters:**
* [German National Team](https://www.ferrero-sammelspass.de/img/shop/Album/998-album.jpg?version=9)
* [Paul Blart: Mall Cop (Der Kaufhaus Cop)](https://image.tmdb.org/t/p/original/5o8kxVsJKw9bdxtsIreBNHSClID.jpg)
* [konzenTRiert (Trier University)](https://www.uni-trier.de/fileadmin/_processed_/1/5/csm_Titelseite_konzenTRiert2021_b65cd70fe6.jpg)
* [Trier](https://www.lieferlokal.de/sites/default/files/styles/1700x2424/public/tr-produktmood-00.jpg?itok=w6Smw1I6)
* [Pills/Tablets](https://www.adworld.ie/wp-content/uploads/2016/09/op.jpg)
* [Seven-Up](https://grist.org/wp-content/uploads/2010/07/ad_7up175baby.jpg)
* [Mario](https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/64f85628578453.55c7bc0a8498b.jpg)
* *Note:* We created the Angry Birds from the second exercise and the Ames Room from the first exercise ourselves.