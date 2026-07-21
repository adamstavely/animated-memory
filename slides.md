# Why It Takes So Long
### Run of Show: 45-Minute Talk for a Non-Technical Audience
 
**Total: ~40 min content + 5 min Q&A. 21 slides.**
Running example threaded through Slides 11 to 16: *"A user uploads a spreadsheet and sees a dashboard."* Marked with [RE] wherever it recurs so you can keep or remove it as a set.
 
---
 
## OPENING (3 min)
 
### Slide 1: Title
**Timing:** 0:30
 
**Graphics:** Full-bleed photo of an iceberg, waterline near the top third so most of the mass sits below. Title text sits in the dark water. Keep it moody, not clip-art.
 
**On-slide words:**
> Why It Takes So Long
> A look under the surface of app development
 
**Speaker notes:** Welcome them, one line on who you are and why you'd know. Set the promise in a single sentence: "By the end of this, when someone tells you a small change will take a month, you'll understand exactly why, and you'll know how to get better answers out of your engineers." Keep it warm. This is a tour, not a defense.
 
---
 
### Slide 2: The button moment
**Timing:** 2:30
 
**Graphics:** A plain app screen with a single button circled in red. Optional speech bubble in the corner: "can you just..."
 
**On-slide words:**
> "Can you just add a button?"
 
**Speaker notes:** Tell the scene everyone in the room has lived. Someone asks for a small change. You say two weeks. The room goes quiet, maybe someone laughs. Name the feeling honestly: it sounds like padding, or slowness, or engineers being difficult. Promise them the real answer is more interesting than any of those, and that the gap between "just a button" and "two weeks" is the whole talk. Land the throughline: "The honest answer to how long will this take is almost always it depends, and that isn't an excuse. It's the actual nature of the work."
 
---
 
## PART ONE: WHAT YOU CAN'T SEE
 
### Slide 3: The iceberg
**Timing:** 5:00 (5 min)
 
**Graphics:** The iceberg again, now with labels. Above water, one small label: "The screen." Below water, stacked labels: storage, business rules, permissions, error handling, logging, testing.
 
**On-slide words:**
> The screen is about 10% of the app.
 
**Speaker notes:** The part people point at, the screen, is the smallest part. Walk them below the waterline. Behind one button: somewhere to store the data, rules about what's allowed, checks on who can do it, handling for when it fails, a record of what happened. Use the restaurant version if the room likes analogies: you order one dish, and behind it is prep, a supply chain, food safety, and a kitchen you never see. The line to land: "Visible simplicity is usually the reward for invisible complexity, not the absence of it." A clean, simple screen often means more work happened, not less.
 
---
 
### Slide 4: Nobody knows exactly what they want yet
**Timing:** 5:00 (5 min)
 
**Graphics:** A simple flow: one plain box "Let users log in" on the left, an arrow fanning out into six smaller boxes on the right (password rules, forgot password, locked accounts, shared email, two devices, account deleted). Show one wish exploding into many questions.
 
**On-slide words:**
> Requirements are discovered, not handed over.
 
**Speaker notes:** The instruction "let users log in" sounds finished. It isn't. Walk the fan-out live: What are the password rules? What happens when someone forgets it? Do we lock an account after failed tries, and for how long? What if two people share an email? Every answer opens a new question. Make the key point for this room clearly: the thinking that turns a vague wish into something precise enough to actually build is real work, even on the days when nothing visible ships. When they see an engineer "just asking questions," that is the work happening.
 
---
 
### Slide 5: The happy path
**Timing:** 3:00
 
**Graphics:** A smooth green path from "Start" to "Done," everything sunny. Small caption: "The demo."
 
**On-slide words:**
> The demo always works.
 
**Speaker notes:** Every demo works, because a demo is the happy path: the one route where everything goes right. The user types what you expected, the network is fine, the data is clean. This is the version people picture when they estimate in their heads. Pause here, because the next slide is the turn.
 
---
 
### Slide 6: Everything that goes wrong
**Timing:** 3:00 (6 min total for happy path)
 
**Graphics:** Same path as Slide 5, now littered with obstacles branching off it: network drops mid-save, 10,000 rows pasted, two people editing the same record, a name with emoji, right-to-left text. Messy on purpose.
 
**On-slide words:**
> "It works" is maybe 20% of the effort.
> "It works when everything goes wrong" is the rest.
 
**Speaker notes:** Now reality arrives. The connection dies halfway through saving. Someone pastes ten thousand rows into a box built for ten. Two people edit the same record at the same second. A name has emoji in it, or reads right to left, and the neat layout breaks. None of this is edge-case trivia. This is where most of the surprising time actually lives. Give this the weight it deserves: the version that works when the world misbehaves is the real product, and it's most of the job.
 
---
 
## PART TWO: THE THREE THAT EAT THE CALENDAR
 
### Slide 7: Section divider
**Timing:** 0:30
 
**Graphics:** Three heavy stone pillars, clean and iconic, labeled Data, Security, Policy. Dark background so they read as "the serious part."
 
**On-slide words:**
> Three reasons things take longer that nobody puts in the meeting.
 
**Speaker notes:** Transition. Tell them the next three are the heavyweights, and they share a trait: they're almost never mentioned when a feature is requested, yet they quietly set the timeline. Warn them gently that this is the densest stretch, and promise a single example to hold onto. Go to the next slide.
 
---
 
### Slide 8: The running example [RE]
**Timing:** 1:00
 
**Graphics:** A dead-simple two-step picture: a spreadsheet icon, an arrow, a dashboard with a couple of charts. Caption underneath: "Sounds like an afternoon."
 
**On-slide words:**
> "Let a user upload a spreadsheet and see a dashboard."
 
**Speaker notes:** Introduce the example you'll carry through all three pillars. It sounds tiny: they upload a file, they see charts. Tell the room to hold that picture, because you're going to watch this one small request pick up time from data, then security, then policy, without ever getting bigger as a feature. This is the spine that makes the abstract concrete.
 
---
 
### Slide 9: Data processing, part one
**Timing:** 3:00
 
**Graphics:** Five different-looking source documents (a spreadsheet, a CSV, a form, a database icon, a PDF) all feeding into one funnel. Above the funnel they disagree; below it, one clean table.
 
**On-slide words:**
> Data is never as clean as people picture it.
 
**Speaker notes:** Data arrives in different formats, with gaps, duplicates, and outright errors. Before anything shows up on a screen, it has to be checked, cleaned, reshaped, moved, and kept consistent across systems that don't naturally agree. Make the reframe stick: "garbage in, garbage out" undersells it. Garbage in means rework, reconciliation, and a lot of quiet effort spent making numbers trustworthy before a single chart exists.
 
---
 
### Slide 10: Data processing, part two [RE]
**Timing:** 3:00 (6 min total for data)
 
**Graphics:** The running example's spreadsheet, zoomed in, with realistic mess highlighted: a blank cell, a date written three different ways, "N/A" in a number column, a duplicate row.
 
**On-slide words:**
> One upload. A dozen decisions.
 
**Speaker notes:** Bring it back to the spreadsheet. What happens when a cell is empty? When dates are written three ways? When someone typed "N/A" where a number should be, or the same row appears twice? Every one of those is a decision someone has to make and then build. The dashboard can't be trustworthy until the data underneath it is, and that's most of the work behind a feature that "just shows the numbers." Land it: the chart is the easy part. Earning the right to draw it is the job.
 
---
 
### Slide 11: Security is a property, not a feature
**Timing:** 3:00
 
**Graphics:** A single lock icon in the center, with faint lines radiating to every other part of a system diagram, showing it touches everything rather than sitting in one box.
 
**On-slide words:**
> Security isn't a task you finish.
 
**Speaker notes:** The instinct is to treat security as a box to tick near the end. It isn't a box, it's a discipline applied to every part of the system: who you are, what you're allowed to touch, keeping data unreadable to the wrong eyes, keeping a record, staying patched. The point that reframes it for a non-technical room comes next, so tee it up: this is different from ordinary bugs.
 
---
 
### Slide 12: Someone is actively trying to break it [RE]
**Timing:** 3:00 (6 min total for security)
 
**Graphics:** Split image. Left: a normal bug (the world being indifferent), a puddle you might slip in. Right: an adversary (the world being hostile), someone deliberately setting a trap. Same outcome, very different cause.
 
**On-slide words:**
> Bugs are accidents. Attackers are on purpose.
 
**Speaker notes:** This is the mental shift. Most problems in software are the world being indifferent: things break by accident. Security is the world being hostile: a person is actively trying to make it fail, and they only need to be right once. Tie it to the example: the moment users can upload files, someone will try to upload something malicious, or peek at another user's data. That's why "make it secure" can't be bolted on at the end. It shapes choices from the first day, it adds review gates, and its absence is precisely what ends up in the headlines.
 
---
 
### Slide 13: Policy and compliance
**Timing:** 3:00
 
**Graphics:** A calendar with a "ready" checkmark on one date, and a separate "approved" stamp landing weeks later. Show two different clocks: engineering time and process time.
 
**On-slide words:**
> Some rules you don't get to code around.
 
**Speaker notes:** Some constraints come from outside the team entirely: legal and regulatory requirements, rules about how long data is kept and who may see it, formal approvals or accreditation before anything can go live. You can finish the build and still wait, because these run on someone else's clock. The message for this audience: a launch date can be set by paperwork and process, not by engineering speed, and pushing the team harder does nothing to move it.
 
---
 
### Slide 14: Policy, the running example [RE]
**Timing:** 3:00 (6 min total for policy)
 
**Graphics:** The dashboard from the example, now with an overlay of questions: "Who's allowed to see this data? How long can we keep the uploaded file? Where is it allowed to live? Who signs off before launch?"
 
**On-slide words:**
> The feature is done. The approvals aren't.
 
**Speaker notes:** Return to the dashboard one last time. Even when it works perfectly, questions remain that engineers can't answer alone: who is permitted to see this data, how long you're allowed to keep the file someone uploaded, where it's legally allowed to be stored, and who has to formally approve it before anyone uses it. Close the example arc: one small request, "upload a spreadsheet, see a dashboard," picked up real time from data, from security, and from policy, and never once got bigger as a feature. That's the gap from Slide 2, made concrete.
 
---
 
## PART THREE: THE REST OF THE ICEBERG
 
### Slide 15: Nothing lives alone
**Timing:** 4:00
 
**Graphics:** Your app as one box in the center, wired to external boxes it doesn't control: a payment provider, another team's system, a third-party service. Some wires drawn frayed or broken.
 
**On-slide words:**
> Your app depends on things you don't control.
 
**Speaker notes:** Modern apps are assembled, not written in isolation. They lean on payment providers, other teams' systems, and outside services that can change or break without warning. A one-line feature can sit finished and blocked because something it depends on isn't ready. You're building one room in a house wired to utilities you don't own.
 
---
 
### Slide 16: Adding people doesn't just add speed
**Timing:** 3:00
 
**Graphics:** Two panels. Left: 2 people, 1 line connecting them. Right: 6 people, a dense web of lines between all of them. Show communication paths exploding, not shrinking.
 
**On-slide words:**
> Nine people can't make a baby in one month.
 
**Speaker notes:** The natural fix for "too slow" is "add people," and it often backfires. More people means more communication, more handoffs, and more ways to step on each other. The web of connections grows far faster than the headcount. Sometimes a bigger team is a slower team. This one tends to genuinely surprise people, so let it breathe.
 
---
 
### Slide 17: It's never really "done"
**Timing:** 3:00
 
**Graphics:** An iceberg again for symmetry, but this time labeled over time: a small "build" tip, and a large submerged "maintain" body: new devices, new rules, new expectations, fixing old shortcuts.
 
**On-slide words:**
> Building is a fraction of the lifetime cost.
 
**Speaker notes:** Shipping is the beginning, not the end. Software rots as the world around it moves: new phones, new regulations, new expectations, and the debt from every shortcut taken under deadline. Maintenance isn't optional cleanup, it's the larger, ongoing part of the cost. The thing you launch has to keep standing in a world that won't hold still.
 
---
 
## CLOSING (3 min)
 
### Slide 18: Section turn to the takeaway
**Timing:** 0:30
 
**Graphics:** Warm shift in tone, lighter background. A handshake or two-arrows-meeting icon. This is the "here's what to do with all this" moment.
 
**On-slide words:**
> So how do you work well with the people who build this?
 
**Speaker notes:** Signal the turn. Everything so far explained the gap. The last few minutes turn it into something they can actually use tomorrow. This is the part they'll remember, so slow down and make eye contact.
 
---
 
### Slide 19: How to be a great partner
**Timing:** 2:00
 
**Graphics:** Three clean icons with short labels: a range (not a single date), a target (the problem, not a chosen solution), a question mark reframed as a green check (questions are progress).
 
**On-slide words:**
> Ask for ranges. Bring problems, not solutions. Treat questions as the work.
 
**Speaker notes:** Give them three concrete habits. First, ask for a range, not a single date, and treat a confident single date with suspicion. Second, bring the problem you're trying to solve, not a solution you've already picked, so the team can find the cheapest path to it. Third, when engineers ask a pile of questions, that's not delay, that's the work getting done in the open. These three change the relationship more than any process does.
 
---
 
### Slide 20: The closing line
**Timing:** 0:30
 
**Graphics:** Near-black slide, one line of text, nothing else. Let it hang.
 
**On-slide words:**
> The most expensive thing you can build is the wrong thing quickly.
 
**Speaker notes:** Say it, then stop talking for a beat. Optionally pair it with the trade-off: fast, cheap, and good is a choice of two, never all three. Thank them, and open it up.
 
---
 
### Slide 21: Q&A
**Timing:** 5:00
 
**Graphics:** Simple. "Questions" and your name or contact. Optionally a faint iceberg watermark to bookend the deck.
 
**On-slide words:**
> Questions
 
**Speaker notes:** Buffer built in. If the room is quiet, seed it: "The one I get most is, why can't we just add more people, so let's start there." Have one or two of your own real examples ready to pull the discussion into their actual world.
 
---
 
### Design notes for whoever builds the deck
- One idea per slide. If a slide needs two thoughts, it's two slides.
- On-slide text is a headline, not a script. The words above are close to the maximum you want visible at once.
- Reuse the iceberg on Slides 1, 3, and 17 as visual bookends so the deck feels like one argument, not twenty separate points.
- The [RE] slides (8, 10, 12, 14) share the spreadsheet-to-dashboard visual. Keep that graphic consistent so the audience recognizes it each time it returns.
 
