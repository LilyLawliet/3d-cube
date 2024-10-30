# 3d-cube
3D cube made with HTML, CSS, And JS

<h1>1. Selecting HTML Elements</h1>
<hr>
<h3>cube: The main container that holds the cube faces and applies rotation. <br>
faces: An object storing each cube face (front, back, right, left, top, bottom) for easy access by name.</h3>

<h1>2. Initializing Rotation Angles</h1>
<hr>
<h3>angleX and angleY hold the rotation angles along the X and Y axes. <br>
These values will be incremented over time to continuously rotate the cube.</h3>

<h1>3. Rotate Cube Function</h1>
<hr>
<h3><b>Purpose</b>: rotateCube is responsible for rotating the cube and updating the shading (lighting) on each face. <br>
angleX += 1 and angleY += 1 increment the angles slightly on each call to create continuous rotation. <br>
<b>CSS Transformation:</b> cube.style.transform = ... applies the rotation by setting a CSS transform with rotateX and rotateY. <br> This rotates the cube along both axes, producing a smooth 3D spinning effect. <br>
<b>updateLighting():</b> After the rotation, this function is called to adjust the shading on each face according to its position relative to a simulated light source.</h3>

<h1>4. Updating Lighting Function</h1>
<br>
<h3><b>Purpose:</b> updateLighting calculates the brightness (or shading) for each cube face based on its angle and applies the shading effect. <br>
<b>lightIntensity:</b> This object contains the brightness value for each face, calculated as follows:
Math.cos(...) calculates the cosine of the angle, representing how much of each face is "facing" the viewer (and light source). <br>
Angles are converted to radians (Math.PI / 180), which JavaScript’s trigonometric functions require.
Minimum Brightness: Math.max(0.6, ...) keeps the brightness at least 0.6, so faces are never too dark.
<b>Dynamic Brightness Application:</b>
For each face, faces[face].style.filter = ... sets the CSS filter: brightness() based on the calculated intensity. This makes faces closer to the viewer brighter and faces further away dimmer, simulating a light source.</h3>
