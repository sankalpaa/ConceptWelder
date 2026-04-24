---
title: "Higher desk. Clearer mind."
date: 2026-01-01
---

<!-- Title Tag -->
<title>Higher desk. Clearer mind | Concept Welder</title>
<head>
    <style>
    .container {
    border: 1px solid #dedede;
    background-color: #a39d87;
    color: #000000;
    border-radius: 5px;
    padding: 10px;
    margin: 10px 0;
    width: 100%
    }
    .quote {
        font-size:medium;
        font-style: italic;
        color: "blue"
    }
    </style>
</head>

# Higher desk. Clearer mind
## I was a prisoner.

At the beginning of my IT career, I dreamed of becoming a network engineer. They moved freely, walking between racks and cables, while programmers stayed glued to their chairs.

Life had other plans. I became a programmer — and for the last 20 years, I’ve been a prisoner of the chair.

## How I Broke the Prison
The first time I saw a height-adjustable table, something clicked. It felt like a simple idea, yet powerful — a way to escape years of sitting without realizing how trapped I had become.

I wanted to buy one immediately. But after looking around, reality set in. The desks were expensive, and none of them truly matched what I needed. They felt like black boxes — closed designs with little room for understanding or customization.

I’ve always enjoyed building things more than buying them. There’s a quiet satisfaction in knowing how something works, in shaping it to your own needs. So instead of purchasing a desk, I decided to build one.

In the end, I built a height-adjustable table with a solid metal frame, powered by two linear actuators and controlled by simple up-and-down switches. It wasn’t just a piece of furniture — it was the moment I finally broke free from the chair.

# Design
## Initial Plan.
Before cutting metal or ordering parts, I needed clarity. Guesswork wouldn’t work here.

I started with a simple question: how much load should this table safely handle? I settled on 50 kg, allowing enough margin for the tabletop, monitors, and everything that would slowly accumulate over time.

Another constraint was space. I didn’t want the new desk to demand more room than the old one. It had to fit naturally into my existing setup. That meant keeping the footprint close to 1200 mm × 600 mm — familiar, comfortable, and proven.

As the design took shape, stability became a recurring thought. Given the size of the table and the expected load, relying on a single lifting point felt like a compromise. That’s when I decided to use two linear actuators, prioritizing balance and long-term reliability over simplicity.

Height came next. The minimum height was dictated by ergonomics — 760 mm for a comfortable sitting position. Standing height was estimated at around 1000 mm. To bridge that range with some room to breathe, I chose 300 mm linear actuators, giving me roughly 60 mm of extra adjustment beyond the basics.

On paper, the plan finally felt right. Now it was time to turn numbers into steel.

## Structure and Main Parts

As the build progressed, the table naturally separated itself into a few core elements. Thinking of it this way made both the design and the troubleshooting easier.

At its heart, the table is made up of four main parts.

### The Skeleton

This is the structure that gives the table its shape and strength.

* The fixed base — a non-moving bottom frame built from metal, responsible for stability and load distribution.

* The moving upper frame — also metal, designed to travel smoothly up and down while staying rigid under load.

* The tabletop — made from waterproof MDF, chosen for its balance between strength, finish, and practicality.

<div class="body-image-wrapper">
    <div class="row body-image-container">
            <img src="{{site.baseurl}}/assets/2026-01-01/height-adjustable-table-bottom.jpg" class="body-image" title="Sketch1">
            <img src="{{site.baseurl}}/assets/2026-01-01/height-adjustable-table-top.jpg" class="body-image" title="Sketch2">
            <img src="{{site.baseurl}}/assets/2026-01-01/height-adjustable-table-top-view.jpg" class="body-image" title="Sketch3">
    </div>
</div>

### The Muscles

Movement comes from the muscles of the system.

* Two linear actuators
(750N, 300 mm stroke, 12 V DC, Speed 10mm/s)

These provide the lifting force, working together to raise and lower the table in a controlled and balanced way.
<div class="body-image-wrapper">
    <div class="row body-image-container">
            <img src="{{site.baseurl}}/assets/2026-01-01/12v-linear-actuator.png" class="body-image" title="Linear actuator">
    </div>
</div>

### The Nervous System

No movement works without control.

<div class="body-image-wrapper">
    <div class="row body-image-container">
            <img src="{{site.baseurl}}/assets/2026-01-01/linear-actuator-controller.png" class="body-image" title="Linear actuator controller">
    </div>
</div>

* The controller circuit — responsible for directing motion and handling user input.

* The power supply — delivering stable power to keep everything moving safely and reliably.

### Design and Mechanical Mistakes I Made

Some lessons are best learned the hard way. This project was no exception.

* Measure twice — then measure again before cutting.
I made several measurement mistakes, especially around overall height. One thing I underestimated was the impact of adding wheels. Even a small change at the bottom affects everything above it.

* Guidance matters more than I expected.
I initially used two steel tubes as guide rails for the moving section. While it worked, it wasn’t ideal. Looking back, using proper linear rails would have provided smoother motion and better long-term reliability.

* Actuator choice is more than just force.
Speed matters. So does smoothness. And if the actuator includes a position sensor, it opens the door to features like preset heights — something I only fully appreciated later.

* Actuator placement and cable management need early planning.
Where you mount the actuators affects stability, alignment, and side loads. Equally important is how power cables move as the table goes up and down. Poor planning here can lead to strain, wear, or failure over time.

* Painting deserves patience.
Painting taught me its own set of lessons. A clean, dust-free environment is essential, and drying time matters more than it seems. One mistake I won’t repeat is mixing methods — hand-painting the first layer and spray-painting the next. The texture from the brush takes a lot of effort to remove later.

# Result
<div class="body-image-wrapper">
    <div class="row body-image-container">
            <img src="{{site.baseurl}}/assets/2026-01-01/first-day-height-adjustable-table.png" class="body-image" title="First day with my height adjustable table">
    </div>
</div>

The first few days were a reminder that change takes time. Standing for even an hour felt tiring, and my body clearly wasn’t used to it. But what surprised me was how quickly that discomfort turned into awareness rather than pain.

As I continued working with the new desk, it started to impress me in quieter ways. I found myself moving more naturally throughout the day. Standing up after long periods of sitting no longer felt like an effort — it happened without thought.

I was no longer locked into a single position. The freedom to shift, stretch, and change posture made long working days feel lighter. Even my eyes felt less tired, simply because I could look around more easily instead of staring at the same fixed point for hours.

In the end, the biggest change wasn’t just the ability to stand — it was the ability to move. And that made all the difference.

# Improvements
* Use high-quality linear rails to guide the upper moving frame for smoother and more stable motion.

* Add lockable wheels to improve mobility without compromising stability.

* Introduce a synchronizer for the linear actuators to ensure perfectly even movement.

* Implement preset height positions for quick and repeatable transitions between sitting and standing.

* Enable PC-based control for height adjustment and automation.

* Add a power backup to handle power failures and allow safe position recovery.


# Conclusion
* Was it worth it?

Absolutely. Without hesitation.

* Who is this for?

This project is for those who enjoy DIY, who are willing to invest time, and who aren’t afraid of small bugs or cosmetic imperfections along the way. It’s for people who find satisfaction in the process, not just the final product.

* What did I learn?

This was the first moving mechanical structure I built from scratch — welding together simple concepts from mechanics, electronics, and electrical engineering. Piece by piece, those concepts came together into something meaningful.


The biggest lesson was this: 

when ideas are welded to action, even simple concepts can turn into something that genuinely supports everyday life. And sometimes, breaking a small prison starts with building something of your own.




