---
icon: dependabot
label: P04.11⠀Introduction
order: 90
---
# :icon-dependabot: Introduction
`Tags:` [!badge Submarine](/projects/P04-submarine.md) [!badge robot-car]()

!!!
To watch it move, check out [Testing](/projects/P04-submarine/P04-30-39-technical-details/P04-34-testing.md).
!!!


*Submarine* is a hybrid 4WD, Bluetooth-controlled competitive robot car. It is capable of collecting and holding solid game pieces of varying profile while moving across the playing field with desired accuracy and excessively high speed.

![](/projects/P04-submarine/media/intro-submarine2.jpg)

Overall frame is constructed with [T-slotted 2020 aluminum framing rails](https://en.wikipedia.org/wiki/T-slot_structural_framing) and compatible profile mounting accessories, features a very unique continuous belt routing elevator using **1:1 gear power transmission technique**.

[!embed](https://youtu.be/us9LYFUomLg)

The robot has two Arduino micro-controller boards, one for propulsion control and one for end effector state switching. Each communicates directly with a separate Android device via a paired Bluetooth module connected to its integrated pins. The boards are programmable using the [Arduino IDE](https://www.arduino.cc/en/software).

Our hybrid wheel setup consists of two regular 65mm tractor wheels as *drive wheels* and two self-manufactured 65mm [omni wheels](https://en.wikipedia.org/wiki/Omni_wheel#:~:text=Omni%20wheels%20or%20poly%20wheels,slide%20laterally%20with%20great%20ease.) as *steering wheels*, which mimics **front axle steering mechanism** and allows for smooth turns while maintaining friction.

<style>
figcaption {
  color: #9D9D9D;
  font-style: italic;
  font-size: 19px;
  padding: 0px;
  text-align: center;
}
</style>
![](/projects/P04-submarine/media/front-axle-steering.gif)<figure>
    <figcaption> Example of simple front axle steering mechanism. Credit: <a href="https://youtu.be/kNf7N4m41UQ">Koshish all time - Youtube</a></figcaption>
</figure>

Our robot was constructed in a 7-week period regarding [M.E.R.C 2023](/projects/P04-submarine/P04-10-19-about-the-project/P04-12-mission.md) tournament. In the end we were eliminated from the competition in the quarterfinals, but we gained a lot of new experiences, insights, and connections, and this was honestly an invaluable experience.

|
--- | ---

<figure>
    <img src="https://64.media.tumblr.com/d103eb823dce2842c673f409f036857b/tumblr_mzx9wrdwFa1snc5kxo1_1280.gifv" alt="Credit: @transparent-angel on Tumblr">
</figure>
