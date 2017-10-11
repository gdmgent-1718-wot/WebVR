# WebVR-Campus
WebVR-Campus | New Media Development | Graphic and Digital Media | Artevelde University College Ghent

# WebVR

## Info

- Contributors: Thomas Coppein & Daan Meert
- Opleidingsonderdeel: Web Of Things
- Academiejaar: 2017-2018
- Opleiding: Bachelor in de grafische en digitale media
- Afstudeerrichting: New Media Development
- Opleidingsinstelling: Arteveldehogeschool

## Deploy

We're using [AFrame.io](https://aframe.io). 

#### 1. Include the script
To include A-Frame we need to drop a script tag with the CDN

```html
<head>
  <script src="https://aframe.io/releases/0.7.0/aframe.min.js"></script>
</head>
```

#### 2. Include a a-scene tag
To add the 3D Boilerplate,VR setup and default controls you just need to add the a-scene tag.
```html
<a-scene>
  ...
</a-scene>
```

#### 3. Add elements to scene
You can add simple elements to the scene:

##### **Add a background (sky)**
```html
<a-sky color="#ECECEC"></a-sky>
```
`For this project we use an image!`
```html
 <a-sky src="Source/VR_Verdiep.JPG" rotation="0 -130 0"></a-sky>
```

##### **Add a cube**
```html
<a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
```

##### **Add a circle**
```html
<a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
```

##### **Add a Cylinder**
```html
<a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
```

##### **Add a plane object**
```html
<a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
```

| Axis  | Description  | Default Value  |
|---|---|---|
| x  | Negative X axis extends left. Positive X Axis extends right.  | 0  |
| y  | Negative Y axis extends down. Positive Y Axis extends up.     | 0  |
| z  | Negative Z axis extends in. Positive Z Axis extends out.      | 0  |


##### **Position the objects**

```html
position="0 0 -4"
```

#### 4. Entity-Component-System (ECS)
A-Frame is an three.js framework with an ECS (Entity-Component-System) architecture.
`A well-known game engine implementing ECS is Unity.`

> - **Entities** are container objects into which components can be attached. Entities are the base of all objects in the scene. Without components, entities neither do nor render anything, similar to empty 'div' s.
> - **Components** are reusable modules or data containers that can be attached to entities to provide appearance, behavior, and/or functionality. Components are like plug-and-play for objects. All logic is implemented through components, and we define different types of objects by mixing, matching, and configuring components. Like alchemy!
> -  **Systems** provide global scope, management, and services for classes of components. Systems are often optional, but we can use them to separate logic and data; systems handle the logic, components act as data containers.

#### 5. ECS in A-Frame

> - **Entities** are represented by the `<a-entity>` element.
> - **Components** are represented by the HTML attributes on `<a-entity>`'s. 
> - **Systems** are represented by `<a-scene>`'s HTML attributes.

```html
<a-entity geometry="primitive: sphere; radius: 1.5"
          light="type: point; color: white; intensity: 2"
          material="color: white; shader: flat; src: glow.jpg"
          position="0 0 -5">
</a-entity>
```
