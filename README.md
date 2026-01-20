# Emmanuel Nyakundi

I think about computers from the bottom up.

Not because it is fashionable, but because the bottom is where the truth lives.
Everything above it eventually lies.

This page exists to explain *how I look at systems*, not to enumerate what I have built.

---

## A point of view

I am interested in systems where:

- latency is not an abstract number but a consequence
- resources are finite, contended, and unfairly distributed
- failures are normal, not exceptional
- correctness is something you *maintain*, not something you “achieve”

I am less interested in APIs and more interested in **contracts**.
Less interested in frameworks and more interested in **boundaries**.
Less interested in scale as a slogan and more interested in **where the cycles go**.

---

## Kernel-adjacent thinking

I spend most of my mental energy close to the kernel, even when I am not writing kernel code.

That means caring about:

- what the scheduler is incentivized to do
- how memory actually moves (or doesn’t)
- when the kernel helps you
- when it silently works against you

“Kernel-adjacent” to me means things like:

- XDP and AF_XDP as *mechanical sympathy*, not just packet speed
- eBPF as a constrained execution environment with sharp edges
- observing systems from inside the kernel instead of guessing from user space
- understanding where abstractions end and undefined behavior begins

I don’t treat these as magic technologies.
I treat them as **interfaces to a very opinionated machine**.

---

## Containers, stripped of marketing

Containers are interesting to me only after you remove the hype.

Once you do that, what remains is:

- processes
- namespaces
- cgroups
- signals
- lifecycle responsibility

Most container problems I see are not about images or orchestration.
They are about **who is responsible when something dies**.

- Who reaps?
- Who forwards signals?
- Who shuts things down?
- Who leaks?
- Who assumes the kernel will clean up after them?

I care about containers only insofar as they force you to answer these questions honestly.

---

## Data planes and fast paths

I am drawn to data planes because they punish sloppy thinking.

Fast paths expose lies immediately:
- one extra cache miss matters
- one extra syscall matters
- one unnecessary copy matters

Working near the data plane teaches humility.
You stop assuming the machine will save you.

---

## Performance, without heroics

I don’t chase performance for bragging rights.

I care about performance because it is how you discover:
- hidden contention
- accidental serialization
- incorrect assumptions
- misplaced trust in defaults

Most performance bugs are not “slow code”.
They are **misunderstood systems**.

---

## How I learn

I learn by reducing systems until they push back.

I remove layers.
I remove conveniences.
I remove safety nets.

Then I wait for something to break and ask *why it broke there*.

I am suspicious of systems that:
- only work when everything is healthy
- only behave under ideal conditions
- only shut down cleanly in demos

The interesting behavior is always at the edges.

---

## What I value

- clarity over cleverness
- invariants over features
- understanding over velocity
- small tools that reveal truth

I don’t optimize for resumes.
I optimize for **not lying to myself** about how systems work.

---

## Writing

I write to document:
- what surprised me
- what assumptions failed
- what I misunderstood for too long

Not tutorials.
Not marketing.
Just notes from the machine.

Blog: https://emmanuel326.github.io

---

## Closing

I don’t believe systems are “complex”.
I believe they are **honest**.

If you pay attention long enough, they tell you exactly what they are doing.

You just have to listen.

