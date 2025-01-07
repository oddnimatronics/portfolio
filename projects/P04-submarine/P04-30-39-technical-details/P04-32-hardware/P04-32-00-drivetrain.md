---
icon: cpu
label: P04.32.00 Drivetrain
---
# :icon-cpu:⠀Drivetrain
`Tags:` [!badge Submarine](/projects/P04-submarine.md) [!badge robot-car]()

<style>
figcaption {
  color: #9D9D9D;
  font-style: italic;
  font-size: 19px;
  padding: 0px;
  text-align: center;
}
</style>

### Framework construction

A common practice in robotics tournaments is to use pre-built kits of parts or even pre-built frames to minimize the time required, and it would be really advantageous to do so. However, in our current country of residence (Vietnam) we can only find robot car kits that look like this:

![](/projects/P04-submarine/media/pre-built-robot-cars-vn.png)

The kits that were available were either too small or too weak for the competition. Additionally, those were not customizable, which would have made it difficult to make changes to the design if necessary.

We therefore decided to build our own robot car chassis from scratch. We chose to use 2020 aluminum extrusion for the frame, as this material is strong, lightweight, and easy to work with.

![](/projects/P04-submarine/media/drivetrain1.jpg)

As for the wheeling system, our team initially used four identical 65mm tractor wheels. However, when operating the vehicle, we observed **car bumps**. Additionally, the car **cannot steer or turn in an expected path**. This is because the friction between the wheels and the ground caused the wheels to grip the ground, and there is no way to guarantee that all wheels would make contact with the ground in the same way.

To address this issue, we learned about the **front axle steering mechanism** in cars and tried to mimic it in our robot. 

![](https://i.stack.imgur.com/ABuf0.jpg)
<figure>
    <figcaption> A 4WD car turns with its two front wheels. Credit: <a href="https://physics.stackexchange.com/questions/183777/car-wheels-in-a-turn">Car wheels in a turn - Physics Stack Exchange</a></figcaption>
</figure>

![](/projects/P04-submarine/media/front-axle-steering.gif)<figure>
    <figcaption> Example of simple front axle steering mechanism. Credit: <a href="https://youtu.be/kNf7N4m41UQ">Koshish all time - Youtube</a></figcaption>
</figure>

To do this in a simpler way, we chose to replace two front wheels with omni wheels. This variation of drivetrain is called **Hybrid 4WD** - 4-wheel drive consists of 2 different pairs of wheel of different type. We began the test with some 48mm and 58mm omni wheels laying around at our work station. However, wheel detachments occurred during test drives. We found that the **circumferential difference** between the remaining wheels at the back (65mm) and our omni wheels (48mm and 58mm) was too large and critical. This is because when the tractor wheels complete a full rotation, the omni wheels have already rotated more than once.

In an effort to find a more suitable solution, we came across a creative approach that involved self-manufacture and mechanical design knowledge.

### Customized omni wheels
!!!
STL files are now available on [Github](https://github.com/oddeyemotion/submarine/tree/main/Hardware/diy-12-roller-omni-wheel) and [Thingiverse](https://www.thingiverse.com/thing:6040100).
!!!

![](/projects/P04-submarine/media/assembled-omni-wheel.jpg)<figure>
    <figcaption>A complete omni wheel: front view (left) and back view (right). Designed to be compatible with hexagonal motor adapter.</figcaption>
</figure>

We discovered open-sourced STL files for [DIY 65mm omni wheels](https://www.thingiverse.com/thing:2202328) online. The majority of the components can be 3D printed, with the exception of some steel rods required to create the center poles for each of the omni wheel rollers, and heat shrink tubing to cover the rollers. Due to the design's advantages and ease of construction, we decided to manufacture a ***test version*** on our 3D printer.

!!!
More info about this test version will be available at [Version archive](/projects/P04-submarine/P04-30-39-technical-details/P04-37-version-archive.md) in future updates
!!!

Upon inspection of the test version, we determined that the diameter of our newly-made omni wheel was still smaller than the tractor wheels. The tractor wheels were actually around **66 to 67mm** in diameter, while our omni wheel was around **62mm** (including the rollers, which were covered). As a result, we had to redesign the omni wheel assembly files from scratch, using the provided STL files as a guide. We used Fusion 360 to create the CAD files.

![](/projects/P04-submarine/media/omni-wheel-calculation.png)<figure>
    <figcaption>New sketch with recalculated measurements. Outer circle (the largest) is 66mm in diameter.</figcaption>
</figure>

![](/projects/P04-submarine/media/omni-wheel-screenshot.jpg)<figure>
    <figcaption>Finalized assemble file. Front view (above) and Back view (below).</figcaption>
</figure>

[!embed](https://youtu.be/T2jld_Z10yM)

We produced new omni wheels with the new files and their diameters fit really close to the tractor wheels' diameters.

![](/projects/P04-submarine/media/omni-wheel-compare.jpg)<figure>
    <figcaption>Size comparison between 65mm tractor wheel and our DIY omni wheel. Upper & lower left: with uncovered rollers. Upper & lower right: with covered rollers.</figcaption>
</figure>

The customized omni wheels enabled us to operate our robot car smoothly and without any car bumps. As a result, steering performance of the car was also improved.

!!!
*Our special thanks to original creator [Christian Haataja](https://www.thingiverse.com/anans1/designs) for sharing his design.*
!!!

|
--- | ---

> The overall construction of our chassis took one week. Final product was a strong and reliable platform that met all of our requirements. We were able to customize the design of the car to meet the specific needs, and we were confident that the chassis would be able to withstand the rigors of competition.

|
--- | ---

<figure>
    <img src="https://64.media.tumblr.com/d103eb823dce2842c673f409f036857b/tumblr_mzx9wrdwFa1snc5kxo1_1280.gifv" alt="Credit: @transparent-angel on Tumblr">
</figure>