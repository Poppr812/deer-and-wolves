# Deer and Wolves

## Background

**Deer and Wolves** is a predator-prey game based on a summer-camp field
game. It combines a simple game of tag with an intuitive demonstration
of how predator and prey populations can rise, overshoot, collapse, and
recover.

The game begins with a fixed population, typically about **21 players**.
An odd total is used deliberately so the deer and wolf populations can
never split evenly. Most players are deer and a small number are wolves.
In the standard starting condition, there is **1 wolf and 20 deer**.

The deer attempt to cross a field from one side to the other while the
wolves try to catch them. What makes the game different from ordinary
tag is that the outcome of each round determines the predator-prey
population of the next round.

A deer caught by a wolf becomes a wolf. A wolf that fails to catch a
deer becomes a deer. The total population therefore remains constant,
but the balance between predators and prey continually changes.

## Core Rules

1.  The game has a fixed, odd total population. A typical game uses **21
    players**.
2.  At the beginning, most players are **deer** and one or a few are
    **wolves**.
3.  Deer begin at one side of the field and attempt to reach the
    opposite side.
4.  Wolves occupy the field and attempt to tag deer before they reach
    safety.
5.  A wolf can catch **no more than one deer per round**.
6.  A deer that is tagged becomes a **wolf for the next round**.
7.  A wolf that successfully catches a deer remains a **wolf for the
    next round**.
8.  A wolf that catches no deer becomes a **deer for the next round**.
9.  A deer that reaches the opposite side without being caught remains a
    **deer**.
10. After each round, the players reset and cross the field in the
    opposite direction.
11. Play continues for many rounds so the changing deer and wolf
    populations can be observed.
12. At least one wolf always remains. If every wolf fails in the same
    round, one of them stays a wolf rather than the predator population
    reaching zero, from which it could never recover.

## The Population Mechanism

The central mechanic is a feedback loop.

When there are many deer and few wolves, wolves have abundant prey and
are relatively likely to make a catch. Successful wolves remain wolves,
and caught deer become wolves. The wolf population therefore tends to
increase.

As the number of wolves increases, the number of deer decreases.
Eventually there may be many wolves competing for very few deer.

At that point, many wolves fail to make a catch. Under the rules of the
game, those unsuccessful wolves become deer. The wolf population can
then collapse rapidly while the deer population rebounds.

The resulting sequence can look something like:

  Round     Wolves     Deer Condition
  ------- -------- -------- --------------------------------
  1              1       20 Abundant prey
  2              2       19 Predator population grows
  3              4       17 Wolves continue expanding
  4              8       13 Competition for prey increases
  5             19        2 Predator overshoot
  6              2       19 Predator population collapses
  7+        Varies   Varies Cycle begins again

The exact numbers depend on player behavior and chance. The important
feature is the **oscillation**, not a predetermined sequence.

## Ecological Concepts

### Predator-Prey Dynamics

Deer represent a prey population and wolves represent a predator
population. The success of each population depends on the size of the
other population.

### Carrying Capacity and Resource Limitation

For wolves, deer are the limiting resource. A large wolf population
cannot be sustained when there are too few deer.

### Overshoot

A successful predator population can expand until it becomes too large
relative to the available prey. This is predator overshoot.

### Collapse

After overshoot, many predators cannot obtain the resources required to
remain predators. The wolf population then falls sharply.

### Recovery

As wolves decline, deer become more numerous. More abundant prey
subsequently creates conditions in which the wolf population can
increase again.

### Negative Feedback

The game contains a self-correcting feedback mechanism:

**More deer → greater wolf success → more wolves → fewer deer → lower
wolf success → fewer wolves → more deer.**

This feedback prevents either population from simply increasing forever.

### Dynamic Equilibrium

The system does not necessarily settle at a fixed number of deer and
wolves. Instead, it can move continually around a changing balance. This
is a useful illustration of a **dynamic equilibrium**.

## Relationship to Predator-Prey Models

The game is conceptually related to mathematical predator-prey models
such as the **Lotka-Volterra equations**.

It is not intended to reproduce those equations exactly. Instead, it
provides a physical and interactive demonstration of the same broad
idea: predator abundance affects prey abundance, and prey abundance in
turn affects predator success.

The game also introduces randomness, individual movement, competition
among predators, and spatial behavior. These make each round different
even when the population counts are identical.

## Digital Game Concept

The digital version preserves the basic camp-game rules while allowing
one player to participate directly.

### Player Control

The human player controls one character by pointing toward a desired
location:

-   **Touchscreen:** drag a finger across the field.
-   **Computer:** click and drag with the mouse.
-   **Keyboard:** WASD or the arrow keys.
-   The character moves toward the indicated point rather than
    teleporting to it, but its speed is deliberately far above that of
    the computer-controlled animals. The player should feel
    unconstrained; the challenge comes from the number of wolves on the
    field, not from sluggish handling.

The player is not restricted to being prey. The player follows exactly
the same conversion rules as everyone else:

-   A player deer that is tagged becomes a **player-controlled wolf** in
    the next round.
-   A player wolf hunts under the ordinary wolf rule and may catch **one
    deer per round**. After that catch the player's hunt is over for the
    round.
-   A player wolf that catches nothing becomes a deer again.

This means a single game moves the player back and forth between the
prey and predator sides of the same feedback loop.

### Starting and Pacing Rounds

Rounds do not begin on their own by default. Each round ends, the
population change is shown, and the game waits for the player to press
**Next Round**. An optional **auto-start** setting advances to the next
round automatically after a two-second pause, for watching the
population cycle run at length without interaction.

### Computer-Controlled Characters

Computer-controlled deer attempt to reach the opposite side while
avoiding nearby wolves.

Computer-controlled wolves pursue available deer. Each wolf stops
hunting after making one successful catch during a round.

### Rounds

Each crossing constitutes one round. At the end of the round:

-   Caught deer become wolves.
-   Successful wolves remain wolves.
-   Unsuccessful wolves become deer.
-   Surviving deer remain deer.
-   The crossing direction reverses.
-   The new population is displayed and the game waits for **Next
    Round**, unless auto-start is enabled.

### Population Display

The game displays the current round number and the current number of
deer and wolves.

Below the field is the **population chart**, which is the real product
of the game. See *The Chart Is the Product*, below.

## Design Principle

The primary design principle is **simplicity**.

The game is interesting because a small number of rules can produce
complex population behavior. Additional features should not obscure the
fundamental feedback mechanism.

The essential loop is:

**Run → Hunt → Catch or Escape → Change Populations → Reverse Direction
→ Repeat**

The objective is therefore both to create a fun chase game and to make
an ecological system understandable through play.

------------------------------------------------------------------------

# Design Direction

*Recorded 10 September 2026. This section supersedes earlier assumptions
about the purpose of the game where the two conflict.*

## Versions

-   **`deer-and-wolves-v1.0.html`** — frozen. Level One complete: the
    camp-game rules, player as deer and wolf, start/auto-start pacing,
    and the two-bar chart. Programmer art.
-   **`deer-and-wolves-v2.0.html`** — frozen. Identical game logic, one
    step up in graphic presentation: animal silhouettes with ground
    shadows, a meadow with woods at each end, running motion and dust on
    a tag, an autumn palette with a serif display face, and a title
    screen.
-   **`deer-and-wolves-v2.1.html`** — current. The canvas is now the
    whole product. See *The Scoreboard*, below.

## The Scoreboard

All controls and readouts moved inside the canvas. There is no HTML
interface left above the field, so the canvas is a single rectangle that
can be dropped into any page or phone screen on its own.

A broadcast-style strip runs across the top of the canvas, in the manner
of a televised sports score bug:

-   **Deer count on the left, wolves on the right**, fixed for the whole
    game. They never swap sides, because a bar chart's job is comparison
    over time and a moving reference frame destroys that.
-   **Round number and the round clock** centred.
-   Pause, restart, and auto-start controls at the right end.

The strip carries no bar of its own. One was built and then removed —
see below.

### A Tug-of-War Bar, Built and Removed

An earlier build put a horizontal tug-of-war bar in the strip: the deer
bar growing rightward from the left edge, the wolf bar leftward from the
right, the seam between them sliding back and forth as the populations
traded places.

It was removed once the end-zone bars existed, because the two were
answering the same question. The end-zone bars show *how many* against a
fixed scale, with history. The strip's bar showed the same counts again
in less space, and its max, min, and usual-range marks were duplicates
squeezed into thirteen pixels.

Two things were genuinely lost, and are worth remembering if the
question comes up again:

-   The seam was a **ratio** read rather than a magnitude read — "who is
    winning" at a glance, legible without understanding an axis.
-   It would have **announced Level Two for free**. Once populations
    begin to breathe, the two halves stop exactly filling the strip — a
    gap opens, or they collide — which is the rule change made visible
    without a word of explanation.

If Level Two makes that second point matter, the bar can come back as a
plain two-colour ratio strip with no ticks and no band.

**The heavy-graphics question is answered by the end-zone bars.** When
one deer remains, the wolf bar stands nearly full height and the deer
bar is a stub. The spectacle *is* the bar; no separate cutscene is
needed.

### Behaviour: Three Layers

Everyone on the field is a child. Same body, same handling, **same turn rate**.
The only physical difference is how fast they run, spread evenly from the
slowest to the fastest across all 21 players. The human player takes the
**second** rung, so exactly one animal out there can outrun them. Speed is a
lifelong trait, so a fast deer becomes a fast wolf.

Turning is shared but **finite**. It has to be: a wolf that commits hard at a
deer and guesses wrong must be able to sail past it, and that overshoot is
where most escapes come from.

**The lines.** Deer line up on the side they are leaving. **Wolves line up on
the side the deer are trying to reach** — the deer have to get through them.
Wolves starting in the middle of the field was wrong and produced a traffic
jam rather than a hunt.

#### Layer 1 — Setup

During the countdown both sides read each other. Most wolves pick a deer and
line up on it; the rest spread out to cover the field. Deer slide toward
whatever part of the wolf line is thinnest.

This needed no special cases for the extremes. With one deer left, every
clustering wolf picks the same animal and they all pile in front of it. With
eighteen deer they fan out across the width. Both behaviours fall out of the
same rule.

#### Layer 2 — The Plan

Each animal commits to a plan before the whistle.

-   **Deer:** go now, follow the crowd, hang back, or swing wide.
-   **Wolves:** charge at the whistle, hold the line and slide sideways, or
    lurk in the middle and take whoever breaks through.

No plan beats the others. Sprinting beats rushers and loses to line-holders;
waiting beats holders and loses to rushers. The clock stops waiting from being
free. A deer abandons its plan if a wolf comes inside panic range.

#### Layer 3 — The Chase

Wolves commit to one deer and **race each other for it**. Nothing divides the
deer up between them. Several wolves breaking for the same animal is precisely
why so many go hungry — predator competition is a source of prey survival, and
modelling it removed the need for an artificial speed handicap entirely.

A deer cuts sideways from the nearest threat. A fast wolf aimed at where the
deer *is* sails past when it cuts, and a wolf arriving from the side takes it
instead.

**A fourth layer is deliberately not built.** Animals could shift their mix of
plans based on what worked last round, producing an arms race under the
population cycle and giving the statistics runs and streaks instead of flat
noise. It is held in reserve, possibly as what distinguishes a later level.

#### A Note on Process

An earlier version tried to produce variation by tuning numbers — speed
ladders, nerve thresholds, a predator handicap — across a dozen measure-and-
adjust cycles. That was the wrong approach twice over: it optimised a
*statistic* rather than how the game feels, and the person who had to judge the
feel never got to play it. **Model the mechanism first; the constants mostly
fall out. If the mechanism is wrong, no constant saves it.**

### How a Round Opens

A round does not begin with everyone sprinting at the whistle. That was
the original behaviour and it was wrong in two ways: it looked nothing
like the real field game, and it left the human player hunting the
screen for their own animal while the round ran on without them.

**The countdown.** Pressing Start holds everyone still for 2.6 seconds
while a large **3 — 2 — 1** counts down *positioned on the player's own
animal*, labelled THIS IS YOU, with the player's ring pulsing. The
number is placed there rather than in the centre of the screen
deliberately: finding yourself is the thing the countdown exists to
solve. The round clock does not start until the count reaches zero.

**The slow watching crawl.** When the count ends, nobody bolts. Each
deer creeps forward at about a quarter speed with its head turning,
watching, and breaks into a run only when one of three things happens:

-   its own nerve runs out (each deer gets a different threshold),
-   enough of the herd is already running to pull it along, or
-   a wolf comes inside panic range.

**Which way they break.** About half the deer are followers, who run
toward wherever the herd is already going. The rest run for the emptiest
ground, away from where the wolves are massed. That split is what
produces the cascade from the real game: a couple break, the wolves
commit to them, and the rest read the new picture before choosing.

**Wolves hesitate too.** Each wolf spends a moment scanning before it
picks a target, and then it prefers a deer that is *running* over a
closer one still standing. Breaking early is therefore genuinely risky,
which is the tension that makes the waiting mean something.

**A balance note worth keeping.** When hesitation was first added, every
wolf caught something almost every round, because a creeping deer is a
sitting target. The population collapsed into a rigid repeating cycle
and the variation the chart exists to show disappeared. The fix was
panic range: deer run faster than wolves (145 against 128), so a deer
that spots an approaching wolf in time escapes. **Panic range is the
whole balance of the game.** Too small and hesitation is simply a death
sentence.

All of these numbers live in one labelled block at the top of the
script, headed *feel of a round*. They are set in code deliberately —
there is no settings panel and no slider.

### The Tally Steps

At the end of a round the counts and the bars do not jump to their new
values. They **step, one animal at a time, spread evenly across one
second** — so a swing from one deer to nineteen rattles through all
nineteen values, while a change of one ticks once.

This matters more than it sounds. The jump showed a result; the stepping
shows the *transfer* — you watch nine deer become nine wolves one at a
time, which is the conversion rule made visible. The scoreboard number
and the end-zone bar height step together from the same value, so they
can never disagree.

Starting the next round early snaps the tally to its final total rather
than leaving it mid-count.

### Touch Control

On a touchscreen the player's animal runs about 55 pixels **above** the
contact point, because a thumb covers whatever it touches. A mouse
pointer hides nothing, so it tracks exactly under the cursor. The offset
is chosen by pointer type, and the existing field clamp keeps the animal
out from under the scoreboard when dragging near the top edge.

### Round Pacing and Controls

-   The round-end prompt appears **on the player's own animal**, wherever
    it happens to be standing, so the mouse never has to travel.
-   **Space** starts a round and pauses one, **P** pauses, **R**
    restarts. The canvas buttons are the touch fallback, not the primary
    path.
### The End-Zone Bars

The population bar chart moved onto the canvas as well. There is no HTML
left on the page at all — the game is one rectangle.

The woods at each end widened to hold a full-height vertical bar: the
**deer bar stands in the left end zone, the wolf bar in the right**,
matching the strip above so the two readouts never disagree about which
side is which. Each bar carries the same four marks as before, labelled
in place rather than in a separate key:

-   bar height — the population right now, with the count above it
-   **MOST** — a tick at the highest it has ever been
-   **FEWEST** — a tick at the lowest it has ever been
-   **USUAL RANGE** — the shaded band it keeps returning to

The bars stand directly on the ground of the end zone with only a faint
ground line beneath them. There is deliberately no container or track
drawn behind them; an empty box around each bar made them read as cages
rather than as populations.

## The Thesis

This is **not a game with a lesson attached**. The goal is not to make
game theory exciting. The goal is to make the **learning** exciting.

The chart is the product. The field exists to generate its data.

A kindergartener and a college student must be able to sit at the same
screen and both get something real. That is achieved by making the thing
itself clear, **not** by layering modes, tutorials, difficulty settings,
or unlockable content.

> **No depth.** Pac-Man has enough depth. Pac-Man never explains itself,
> has no tutorial, and no one has ever needed one. That is the standard.

## The Chart Is the Product

The line graph is replaced by a **two-bar chart**: one bar for deer, one
bar for wolves. Each bar carries four pieces of information.

  Mark               Meaning                       Plain language
  ------------------ ----------------------------- ---------------------
  Bar height         Current population            "right now"
  Upper tick         Highest ever reached          "most ever"
  Lower tick         Lowest ever reached           "fewest ever"
  Shaded band        Mean ± 1 standard deviation   "usual range"

The shaded band is the heart of the whole design. **Dynamic equilibrium
is not a definition to be read; it is a band the bar keeps leaving and
keeps coming back to.** A five-year-old watching the bar climb out of
the band and fall back into it has understood dynamic equilibrium
without being told the term. A college student reading the same band
sees a standard deviation.

Nobody is talked down to and nobody is locked out. One screen, one
chart, no modes.

The vocabulary the game intends to hand someone: **cycle**, **peak**,
**crash**, **usual range**, **overshoot**.

## The Drama

The spectacle and the lesson must be the same event.

When the wolves take nearly every deer and one deer remains, the screen
goes **heavy with wolves** — thick with them, crowded, loud. The
following round those wolves starve, and the screen **floods with deer**
as the prey population rebounds into the empty field.

That swing *is* overshoot and collapse. It is not an illustration of
overshoot and collapse. The player feels the mechanism rather than
reading about it.

**Open question:** whether the heavy-graphics moment (a) takes over the
screen between rounds as punctuation, (b) washes over the live field
while play continues, or (c) erupts outward from the bar itself. Option
(b) is the most impressive; option (a) is the easiest to read.

## Replay Comes From the Setup Screen

Replay value comes from **adjustable starting conditions**, not from
scores, streaks, or progression.

-   Default start: **21 players, 3 wolves, 18 deer**.
-   A setup screen allows those numbers to be changed, scaling up to
    hundreds per side.
-   Additional settings expose the genuine scientific variables of the
    system rather than arbitrary difficulty knobs.

## The Three Levels

Three systems, one chart, **the same curve every time**. This repetition
is the payload: by the third level the learner sees that the shape has
nothing to do with animals. That realization is what holds a college
student.

### Level One — Deer and Wolves

The camp game exactly as specified in the first half of this document.
Total population is fixed; a tagged deer becomes a wolf, a hungry wolf
becomes a deer.

Because the total is locked, the two bars are mathematical mirrors of
each other. This is a real limitation and it is accepted at this level
for the sake of the clean rule.

### Level Two — Populations That Breathe

Introduces the concept that **a population can grow when nothing is
eating it**.

Surviving deer reproduce; wolves that go hungry for too long die rather
than converting. The total is no longer fixed and the two bars move
independently.

This unlocks the single most important fact in predator-prey ecology:
**the wolf peak arrives after the deer peak.** Predators always lag
their prey. The fixed-population rule of Level One mathematically
forbids this lag, which is why Level Two must exist.

### Level Three — Rats and Apples

The food does not run away. The only variables that matter are how fast
rats breed and how much food exists.

**You are always a rat.** The mechanic:

-   You run to find a **mate**.
-   Mating produces a family. **You then become one of the offspring**
    and continue playing.
-   Do this three times within the round's time limit and the field
    holds exponentially more rats. Four times and it is a swarm.

This solves the hardest problem in the design. A single player cannot
feel exponential growth, because a person is one animal. Making the
player the **lineage** rather than the individual fixes it: four
generations in, the swarm on the field is the swarm you personally made.

Meanwhile the apples grow on their own cycle. As rats multiply, each rat
finds it harder to eat. When the apple cycle slows, the rats starve and
the population falls back to a small remnant — and it begins again.

**Real-world grounding:** this models *mautam* in Mizoram, northeast
India, where a bamboo species flowers roughly every 48 years, drops an
enormous seed crop, rats breed explosively on it, and the swarm then
turns on the rice crop. Famine follows. Australian mouse plagues follow
the same logic after large grain harvests.

**The farmer** plants and cultivates apples, with seasonal yield feeding
the rat population. **Decided: the farmer is computer-controlled.** The
game is one human player against the computer throughout. Multiplayer is
explicitly out of scope for now.

## Known Constraints

-   **Rendering the swarm.** Several hundred rats cannot be drawn as
    several hundred individual circles. A swarm must be rendered as a
    swarm. This is solvable but it shapes the art direction and should
    be decided before art is commissioned.
-   **Statistics need history.** The usual-range band is meaningless
    until several rounds have been played. It should not appear before
    it means something.

## Build Order

1.  Level One with the two-bar chart. The band either reads instantly or
    it does not, and no amount of discussion settles that question.
2.  Resolve the remaining open question: the heavy-graphics treatment.
3.  The setup screen and large populations.
4.  Level Two.
5.  Level Three.
6.  Art, sound, and the swarm renderer.

Art and sound are deliberately last. They are premature until the band
proves it works.

## Distribution

The game is a single self-contained HTML file with no dependencies or
build step. It runs on any phone, tablet, or computer with a browser.

-   **Sharing now:** publish to a private Artifact URL, or host the file
    free on GitHub Pages, Netlify, or Cloudflare Pages for a permanent
    public link.
-   **Feeling like a real app:** add a PWA manifest and service worker.
    The page then installs to a phone's home screen with its own icon,
    launches full-screen without browser chrome, and works offline.
-   **The App Store** is not recommended. It requires a native wrapper,
    an annual developer fee, and review cycles, and returns very little
    that a PWA does not already provide.
