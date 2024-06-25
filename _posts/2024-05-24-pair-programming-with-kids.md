# Pair-programming with Kids

As a dad, I want to teach my kids the things I learned later in life, hoping they get a head start. One day, I decided to introduce my three kids to the world of programming, starting with HTML because I thought it would be easy. To my surprise, only one of them was interested.

I am always inspired by watching Dr. Ruchira Wijerathna's  ['Science With Ruchira'](https://www.youtube.com/@ScienceWithRuchira) YouTube channel. One day, I showed my kids his ['DIY Arduino RC Car'](https://www.youtube.com/watch?v=T7A0ICf_pa4) video (In Sinhala Language), as they are big fans of vehicles. 

[![Watch the video](./assets/2024-05-24/DIY%20Arduino%20RC%20Car%20%20-%20Sceince%20with%20Ruchira.PNG)](https://www.youtube.com/watch?v=T7A0ICf_pa4)

After watching the video, they asked me, "Can't we build one?" I thought it was a great opportunity to introduce them to programming and the basics of project management. 
I said, "Yes, you can build it yourselves. I can help." 
Their next question was, "How can we build such a vehicle ourselves?"

When I heard their question, I remembered what I learned from [Johanes Broadwell](https://github.com/jhannes) 10 years ago, He taught us that any project (or any task in a big project) can be achieved by breaking it down into four steps.
1. Experimental version
2. Basic version
3. Simplified version
4. Complete version
5. Enhanced version (Optional)

 Johannes wrote about that experimental approach in his blog under [Pair programming with Sankalpa](https://johannesbrodwall.com/2014/06/27/pair-programming-with-sankalpa/).
I applied the same technique in several software projects, and I have personally found it very effective.

I said 'Yes, you can build that in 4 steps'. 
1. Experimental jeep version.
2. Basic jeep version.
3. Simplified jeep version.
4. Complete jeep version.
5. Enhanced jeep version. (Optional)

Lets call it 'jeep', they named it.

Our goal was to build an all-terrain vehicle with a camera for real-time viewing.

First we started experimental jeep version. 

This phase's milestone is to have something controlled by an Arduino board.

To start the project, we checked what we had on hand. We had only one NodeMCU board and a laptop. I suggested ordering differentials and other required parts for the Jeep online, even though it might take some time for them to be delivered. But the kids said, "No, we have a differential from an old toy. We can build the chassis ourselves," the brothers insisted.

![Items found from home](././assets/2024-05-24/Items%20in%20hand.jpg "Items found from home")

![Front axle](../assets/2024-05-24/Front%20axle.jpg "Items found from home")

![Rear axle](./assets/2024-05-24/Rear%20axle%202.jpg "Items found from home")

After spending 1-2 days on mechanical work, they came back with a chassis built from plastic bars, two different types of wheels, and a working front axle. The vehicle wasn't very solid, but it was enough for an experimental version. The front axle consisted of two motors: one for moving forward and backward, and another for turning left and right.

Then we tested both axle mechanisms and found that only the front axle was working completely. The rear axle had some mechanical issues, but it was enough to build an "experimental", "simplified" or "simplified" version of the Jeep.

And could find two 1200mah batteries from old emergency lamp.

Next, we got started with the Arduino IDE and try to understand simple code. We used the [Ardunio Blink LED](https://docs.arduino.cc/built-in-examples/basics/Blink/) sample.
 
Taking it one step further, we planned our real code. I asked them to write some pseudocode for the program. The elder brother had already learned this in school, and what they wrote was acceptable.

Pseudo code
![Pseudo code](./assets/2024-05-24/Pseudo%20code.jpg "Pseudo code")

That was the first virtual sprint we ran.

We started the next sprint by preparing other required items. We bought an L298N motor controller and other necessary parts from a nearby electronics shop, and they completed the wiring.

Next, it was pair programming time. We needed to program our vehicle for actions: forward, reverse, turn left, and turn right. Together at one desk, I showed them how to program the vehicle to go forward. Then, with my help, they programmed it to reverse. They managed to program it to turn left and right by themselves. After a few rounds of testing and bug fixing, they achieved that.

As all the vehicle's actions were handled by a single function, I thought it was a good time to introduce 'Code Refactoring.' Together, we created the first custom function to handle the forward action. After they completed the other three functions, we marked the end of the second sprint.

And also that marked the completion of the first step, the 'Experimental Jeep Version,' of this project.

They egally wating for to controll there 'jeep' remotly. And already watching some vedios how to do that have found they can do that using 'Blnk' platform.
['Blink'](https://blynk.io/)

First our plan was to build a web page and controlled 'jeep' over that, But I thought 'Blnk' is easy to understand and less complecated for them. 
Then we installed required library, download mobile app, and modify the code to support 'Blnk' with only forward action. 
Code compiled but failed to upload to the module. Trying few more time but result was same.
Then we found issue is with board, we were using CH340 board which is less reliable than CP2102 board. 
We have to wait about 5-6 days till the new board received. 

NodeMcu V3 Lua CP2102 ESP8266 Development Board
![New board](./assets/2024-05-24/CP2102%20ESP8266%20board.jpg "NodeMcu V3 Lua CP2102 ESP8266 Development Board")

Re-start the project again, upload the code and tested. But 'jeep' only going forward, no turning or even not stopping regardless of what ever the command we sent. 
First we thought issue with the wiring, but later found issue with code it self. 
In code refactring they have copy and paste the same values to every function. 
Finally its working. 
They built there own remote controlled car. 

![Pseudo code](./assets/2024-05-24/Completed%20top%20view.jpg "Completed top view")
![Pseudo code](./assets/2024-05-24/Completed%20Front%20view.jpg "Completed front view")
I am going to stop here with the end of Basic jeep version. 
Simplified and complete version yet to come.



