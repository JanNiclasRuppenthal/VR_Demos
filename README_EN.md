[Deutsche Version](README.md) | [English Version](README_EN.md)

---

# EcoDive: Save The Ocean
**Developers:**
- Michael Feldmann 
- Philipp Geier
- Jan Niclas Ruppenthal

This project is the final project for the module "VR and 3D Interactions". Additionally, it was submitted as a demo for VRST 2024.

## Game Description
In our game EcoDive, the player must collect trash in an underwater world. Movement is controlled using a Diver Propulsion Vehicle (DPV), and a radar can be used to locate and collect the trash.
However, it is impossible to win this game, regardless of how much trash has been collected beforehand. This mechanic is intended to illustrate the futility of collecting trash. It aims to emphasize that the waste should not enter marine environments in the first place.

## Selected Themes
For our game, we decided on the following themes:
- Sustainability
- Fostering Empathy
- Education and Awareness

## Technical Effort
Our game EcoDive features a simulation of over 3000 corals, and we have implemented infinite terrain generation. For marine life, a simple flocking simulation was implemented to make the underwater world feel immersive and authentic.

## Content Delivery
To convey the game's content as authentically and immersively as possible, visibility is degraded through the use of fog and a gradual grayscale effect via post-processing. The vitality of marine life (fish, corals, and turtles) depends on the player's activity: the less trash collected, the more creatures die. To enhance immersion, breathing is simulated using a sine wave or microphone input. This is visualized using a particle system. At the end of the game, the player finds themselves in a room where a factual video is played. The video aims to raise awareness about the issue of marine debris and its far-reaching consequences.

## Usability and User Experience
To locate trash in the underwater world, the radar on the left controller can be used. To improve the visibility of trash near colorful corals, a red outline was added to these objects. Movement is achieved via pointing-based steering with 3-DOF translation and physical rotation using a linear function with a maximum speed of 5 m/s. The game can be restarted at the end via a button.

## Use of 3D Interactions and Multimodal Feedback
The trash can be grabbed and collected using the controllers. While moving through the simulated underwater world, the controllers vibrate depending on the current speed.

## Key Bindings
- **Grab:** Trash and the DPV handle can be grabbed using the grip button.
- **Movement:** When grabbing the DPV with at least one controller, the right trigger can be used to adjust the DPV's speed.
- **Rotation:** If safe physical rotation cannot be guaranteed, the thumbstick on the right controller can be used for horizontal rotation.
- **UI Interaction:** By pressing a UI button with the controller.



# Used external libraries:

## Virtual Reality und 3D Interactions:
- XR Interaction Toolkit

## In-Game Sound::
- [Atmosphere](https://freesound.org/people/Xemptful/sounds/406623/)
- [Air Bubbles](https://freesound.org/people/ristooooo1/sounds/539819/?page=2#comments)

## Spielszene:
- Living Beings
    - [Turtle](https://sketchfab.com/3d-models/sea-turtle-23dcb315dea44f5082b020b04710bd31)
    - [Fish](https://assetstore.unity.com/packages/3d/characters/animals/fish/emperor-angelfish-263329)
    - [Coral 01](https://sketchfab.com/3d-models/koraller-snm21005-d385ddbdef4340a2b0ee48eab81b785f)
    - [Coral 02](https://sketchfab.com/3d-models/lowpoly-coral-pack-29d5be0e220f48818346cabfa065e887)

    - Garbage:
        - [Garbage Bag](https://sketchfab.com/3d-models/low-poly-trash-bag-69876d51e2f0462498b81dffe3387ae0#download)
        - [Can](https://sketchfab.com/3d-models/tin-cans-ff0665ece31d4c4eb6182a4756c583bf)
        - [Kefir](https://sketchfab.com/3d-models/kefir-bottle-fe82b4f4286a48f294ebf05f8d264691)
        - [Yogurt](https://sketchfab.com/3d-models/yogurt-7cf010b5a4d245c8ae07be585aadc2b8#download)
        - [Bottle](https://sketchfab.com/3d-models/bottle-f06024f0949b4f78afd60b879fee9de9)
        - [Dented Can](https://assetstore.unity.com/packages/tools/modeling/mess-maker-free-213803)

## Game Over Raum (Video und Sound):
- Images:
    - [Image 01](https://pixahive.com/photo/__trashed-32113/)
    - [Image 02](https://pixahive.com/photo/plastic-bottle-and-plastic-bags-on-ocean-floor/)
    - [Image 03](https://pixahive.com/photo/a-polluted-river-8/)
    - [Image 04](https://pxhere.com/en/photo/1365482)
    - [Image 05](https://pxhere.com/en/photo/558663)
    - [Image 06](https://pxhere.com/en/photo/1611355)
    - [Image 07](https://pxhere.com/en/photo/428305)
    - [Image 08](https://pxhere.com/en/photo/1414425)
- Facts:
    - [Fact 01](https://en.nabu.de/topics/ecosystems/ocean-trash.html)
    - [Fact 02](https://www.unep.org/plastic-pollution)
    - [Fact 03](https://www.europarl.europa.eu/pdfs/news/expert/2018/10/story/20181005STO15110/20181005STO15110_en.pdf)
    - [Fact 04](https://www.science.org/doi/10.1126/science.aar3320)
- [Sound](https://freesound.org/people/guitarman213/sounds/707899/)

## Sonstige Ressourcen:
- [Quick Outline](https://assetstore.unity.com/packages/tools/particles-effects/quick-outline-115488)
- [Mass Spawner](https://assetstore.unity.com/packages/tools/terrain/mass-spawner-object-placement-tool-191111)
- [Double-Sided Shader](https://assetstore.unity.com/packages/vfx/shaders/free-double-sided-shaders-23087)
- Post Processing
- TextMeshPro