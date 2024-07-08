<div class="row">
    <div class="col-md-12 header-banner">
        <img src="{{site.baseurl}}/assets/2024-05-24/page_banner.jpg" title="Pair-programming with Kids" width="33%">
    </div>
</div>
    
# Pair-programming with Kids

As a dad, I want to teach my kids the things I learned later in life, hoping they get a head start. One day, I decided to introduce my three kids to the world of programming, starting with HTML because I thought it would be easy. To my surprise, only one of them was interested.

I am always inspired by watching Dr. Ruchira Wijerathna's  ['Science With Ruchira'](https://www.youtube.com/@ScienceWithRuchira) YouTube channel. One day, I showed my kids his ['DIY Arduino RC Car'](https://www.youtube.com/watch?v=T7A0ICf_pa4) video (In Sinhala Language), as they are big fans of vehicles. 

<div class="row body-image-wrapper">
    <div class="col-md-12 body-video">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/T7A0ICf_pa4?si=fQ-Fly_rihbAxKSs"
            title="YouTube video player" frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
</div>

After watching the video, they asked me, 

"Can't we build one?" 
I thought it was a great opportunity to introduce them to programming and the basics of project management. 

I said, "Yes, you can build it yourselves. I can help." 

Their next question was, "How can we build such a vehicle ourselves?"

When I heard their question, I remembered what I learned from [Johanes Broadwell](https://johannesbrodwall.com/about/) 10 years ago, He taught us that any project (or any task in a big project) can be achieved by breaking it down into four steps.
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

To start the project, we checked what we had on hand. We had only one NodeMCU board and a laptop. I suggested ordering differentials and other required parts for the Jeep online, even though it might take some time for them to be delivered. 
But the kids said, "No, we have a differential from an old toy. We can build the chassis ourselves," the brothers insisted.

<div class="body-image-wrapper">
    <div class="row body-image-row">
        <div class="col-md-12 body-image-title">Items found from home</div>
    </div>
    <div class="row body-image-container">
<!--         <div class="col-md-4"> -->
            <img src="{{site.baseurl}}/assets/2024-05-24/Items%20in%20hand.jpg" class="body-image" title="Items found from home">
<!--         </div>
        <div class="col-md-4"> -->
            <img src="{{site.baseurl}}/assets/2024-05-24/Front%20axle.jpg" class="body-image" title="Items found from home">
<!--         </div>
        <div class="col-md-4"> -->
            <img src="{{site.baseurl}}/assets/2024-05-24/Rear%20axle%202.jpg" class="body-image" title="Items found from home">
<!--         </div> -->
    </div>
</div>

After spending 1-2 days on mechanical work, they came back with a chassis built from plastic bars, two different types of wheels, and a working front axle. The vehicle wasn't very solid, but it was enough for an experimental version. The front axle consisted of two motors: one for moving forward and backward, and another for turning left and right.

Then we tested both axle mechanisms and found that only the front axle was working completely. The rear axle had some mechanical issues, but it was enough to build an "experimental", "simplified" or "simplified" version of the Jeep.

And could find two 1200mah batteries from old emergency lamp.

Next, we got started with the Arduino IDE and try to understand simple code. We used the [Ardunio Blink LED](https://docs.arduino.cc/built-in-examples/basics/Blink/) sample.
 
Taking it one step further, we planned our real code. I asked them to write some pseudocode for the program. The elder brother had already learned this in school, and what they wrote was acceptable.
That was the first virtual sprint we ran.

<div class="body-image-wrapper">
    <div class="row body-image-row">
        <div class="col-md-12 body-image-title">Some of their notes <I>(in their own words)</I></div>
    </div>
    <div class="row body-image-container">
        <div class="col-md-3">
            <a href="{{site.baseurl}}/assets/2024-05-24/age_8_day1.jpg" target="_blank" >
                <img src="{{site.baseurl}}/assets/2024-05-24/age_8_day1.jpg" class="body-image" title="Day 1">
            </a>
                        <span class="body-quated-text">'
            Day 1
            when I was watching a 
            video I found this
            video about a Remote control
            jeep I thout I could play
            with it all day so I startet
            to make it with my brother
            first he told he will show
            how to do it after lots of
            work it looked like this'
            </span>
        </div>
        <div class="col-md-3">
            <a href="{{site.baseurl}}/assets/2024-05-24/age_8_day2.jpg" target="_blank" >
                <img src="{{site.baseurl}}/assets/2024-05-24/age_8_day2.jpg" class="body-image" title="Day 2">
            </a>
                        <span class="body-quated-text">
            'Day 2
            So after that we had all set
            not all because we had to
            programe if we didn'
            programe nothing would happen
            so we programe it was hard
            to programe all the stuff
            because if had a small
            mistake we have to do it
            again so we programe it all
            day so now the hard
            part was over we had
            to put the programe
            it to the Node MCU'</span>
        </div>
        <div  class="col-md-3">
            <img src="{{site.baseurl}}/assets/2024-05-24/age_8_sketch.jpg" class="body-image" title="Items Sketch">
            <span class="body-quated-text">Some sketch</span>
        </div>
        <div  class="col-md-3">
            <img src="{{site.baseurl}}/assets/2024-05-24/Pseudo%20code.jpg" class="body-image" title="Pseudo code">
            <span class="body-quated-text">Pseudo code</span>
        </div>
    </div>
</div>

We started the next sprint by preparing other required items. We bought an L298N motor controller and other necessary parts from a nearby electronics shop, and they completed the wiring.

Next, it was pair programming time. We needed to program our vehicle for actions: forward, reverse, turn left, and turn right. Together at one desk, I showed them how to program the vehicle to go forward. Using this function vehicale could go forward to given time.

 Then, with my help, they programmed it to reverse. They managed to program it to turn left and right by themselves. After a few rounds of testing and bug fixing, they achieved that.
Then we had a 'jeep' which run forward few seconds, then reverse back and turn left and right by it self. No action can be controll remotly. 

As all the vehicle's actions were handled by a single function, I thought it was a good time to introduce 'Code Refactoring.' Together, we created the first custom function to handle the forward action. After they completed the other three functions, we marked the end of the second sprint.

And also that marked the completion of the first step, the 'Experimental Jeep Version,' of this project.

My initial plan was to build a webpage to control the vehicle. However, when I mentioned this, their faces didn't look enthusiastic. They had already watched some videos and had ideas about other solutions. They said, 

"We saw something called B_ly_nk. Can't we use that?" 
After thinking for a moment, I realized they were right. They were eager to control their vehicle remotely, and building a webpage might be too complicated, potentially causing them to lose interest in the project. 

So, I said, "Yes, let's use ['Blink'](https://blynk.io/)

<div class="body-image-wrapper">
    <div class="row body-image-row">
        <div class="col-md-12 body-image-title">Some of their notes <I>(in their own words)</I></div>
    </div>
    <div class="row body-image-container">
        <div class="col-3 col-md-3">
            <a href="{{site.baseurl}}/assets/2024-05-24/age13-day1.PNG" target="_blank" >
                 <img src="{{site.baseurl}}/assets/2024-05-24/age13-day1.PNG" class="body-image" title="Day 1">
            </a>
            <span class="body-quated-text">'
            Day 1
            I found some pices and puted It to gathed and end of day I tryed three types of metila and It was like this
            </span>
        </div>
        <div class="col-3 col-md-3">
            <a href="{{site.baseurl}}/assets/2024-05-24/age13-day2.PNG" target="_blank" >
                <img src="{{site.baseurl}}/assets/2024-05-24/age13-day2.PNG" class="body-image" title="Day 2">
            </a>
            <span class="body-quated-text">
            'Day 2
                found out what to bring from the shop and went to the shop and setup them to together and made the cirtes and foude out a box to put the cirtes and set it in the jeep now'
            </span>
        </div>
        <div class="col-3 col-md-3">
            <a href="{{site.baseurl}}/assets/2024-05-24/age13-day4-5.PNG" target="_blank" >
                <img src="{{site.baseurl}}/assets/2024-05-24/age13-day4-5.PNG" class="body-image" title="Day 4 and 5">
            </a>
                <span class="body-quated-text">'
                day 4
                I have being forgat are about the Jeep and my father remind me.
                day 5
                I checked out the old program and I did some modeficaion and we need to make the remot in the "Blenk" app and my e-mail Password is not working we stop of the day'
                </span>
        </div>
        <div class="col-3 col-md-3">
            <img src="{{site.baseurl}}/assets/2024-05-24/age13-sketch.PNG" class="body-image" title="Items Sketch">
            <span class="body-quated-text">Some sketch</span>
        </div>
    </div>
</div>

Blynk is easy to understand and less complicated for them. We installed the required library, downloaded the mobile app, and modified the code to support it. First, we tested it with only the forward action. The code compiled but failed to upload to the module. After trying a few more times with the same result, we discovered the issue was with the board and the same problem occurred with other similar boards. We found that we were using CH340 boards, which are less reliable than CP2102 boards. We had to wait about 5-6 days until the new CP2102 board arrived 

We restarted the project the day the new board arrived, uploaded the code, and tested it. We tested the forward action first through the Blynk app, and it worked. Then, they had to complete the other actions. After an hour or so, they came back complaining that even when they tried to reverse or turn left or right, the 'Jeep' only went forward.

We started debugging by first checking the wiring to ensure there were no issues. Then, we began checking the code. We found that we had four different functions for each action, but all the actions were identical. At first, I wondered how this happened since we had already tested our 'Jeep' actions in the second sprint. Later, I realized that the issue occurred after the code refactoring, and we hadn't run any unit tests since then.

We corrected the code, and finally, it worked. I still remember their faces after successfully owning their own built remote-controlled 'Jeep.'

I am going to stop here with the end of the Basic Jeep version. The simplified and complete version is yet to come.

When the pupil is ready the teacher appears.
 
Happy pair programming!

<div class="body-image-wrapper">
    <div class="row body-image-row">
        <div class="col-md-12 body-image-title">Some captures</div>
    </div>
    <div class="row body-image-container">
        <div class="col-md-4 col-md-4">
             <img src="{{site.baseurl}}/assets/2024-05-24/Completed%20Front%20view.jpg"  class="body-image" title="Completed front view">
              <span class="body-quated-text">Completed front view</span>
        </div>
        <div class="col-md-4 col-md-4">
            <img src="{{site.baseurl}}/assets/2024-05-24/Completed%20top%20view.jpg"  class="body-image" title="Completed top view">
            <span class="body-quated-text">Completed top view</span>
        </div>
        <div class="col-md-4 col-md-4">
            <img src="{{site.baseurl}}/assets/2024-05-24/CP2102%20ESP8266%20board.jpg"  class="body-image" title="NodeMcu V3 Lua CP2102 ESP8266 Development Board">
            <span class="body-quated-text">NodeMcu V3 Lua CP2102 ESP8266 Development Board</span>
        </div>
    </div>
</div>
