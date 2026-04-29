---
title: As AI Models Get Stronger, What Gets Absorbed and What Endures
date: 2026-04-29
categories: [Thinking]
tags: [AI, Agent, Strategy]
---

Over the past year, the most honest feeling in AI has not been excitement about a stronger model. It has been the sense that whole layers of engineering are getting thinner.

A few months ago, people still spent serious time on prompt tricks, agent orchestration, context management, tool routing, and all the glue around retrieval. Then a new model arrived and swallowed a good part of that work. That is where the anxiety comes from. If models keep moving upward, what happens to the things you spent six months or a year building? Do they turn into a single line in a future release note?

That question runs deeper than whether one product will survive. It gets at something harder: in a system where base capability keeps climbing, can human effort still compound? Can engineering work still turn into durable value?

I keep coming back to one phrase for this pattern: capability collapse.

I do not mean that all applications disappear. I do not mean that every middle layer dies. I mean that models keep absorbing abilities that used to live outside the model. In older software stacks, you could picture a clean structure: infrastructure at the bottom, frameworks in the middle, applications on top. In the model era, the middle is unstable. It gets compressed as model capability rises, then it grows back somewhere else.

## Start with the symptoms

If you break the last few years into stages, the shift is easy to see.

Around 2023, many teams spent their time on prompt templates, memory systems, tool routers, and retrieval pipelines. That made sense. Models were weaker, their reasoning chains were shorter, their context windows were smaller, and many useful behaviors had to be built around them. People assumed the teams with the best scaffolding would push models the furthest.

Then the ground moved. Models got better at tool use. Longer context became usable. Reasoning chains became more reliable. Planning improved. Those earlier engineering patterns did not disappear overnight, but their value per unit of effort dropped fast. Work that once needed a pile of glue code started to happen inside the model.

The same thing showed up in coding tools. Early AI coding products won by doing things raw models could not do well enough. They gave the model better access to the repository, better file discovery, better edit organization, better context control. Once model vendors started shipping coding agents that could read a codebase, edit files, run commands, inspect the output, and keep iterating, the tool layer got pushed into a harder question. Are you selling a real workflow, or are you selling a more convenient shell around the model?

That is why the discussion around Cursor, Claude Code, and the rest of the AI IDE field has felt so charged. The uncomfortable part is not that one system outperforms another. The uncomfortable part is that model vendors have started walking downstream into territory that used to belong to the tool layer. Once that happens, everyone building in the middle sees the same thing at once: their position was never as stable as it looked.

You can see the change in what the industry talks about. Early conversations obsessed over prompt writing, clever orchestration, and flashy demos. The discussion now leans toward evaluation, permissioning, rollback, audit trails, workflow design, context boundaries, and verification. That change matters. It tells you the model is no longer just a system that answers questions. It is entering real environments and colliding with real constraints.

## Why models keep moving upward

One reason is technical. A large language model is not a single-purpose tool. It is a general capability substrate.

Databases changed application design. Cloud computing changed deployment. Mobile internet changed distribution. None of those layers tried to pull understanding, planning, and execution into the same place. Models do. A strong model can read language, write code, plan steps, call tools, and operate across long context. Work that used to sit in separate layers starts getting pulled into one core system.

There is a useful historical parallel here. Early programmers had to work closer to the machine. As compilers improved, they absorbed more of that complexity. Register allocation, optimization, and part of memory management stopped being front-line labor for the programmer. The programmer did not get lazier. The abstraction moved. Models are doing something similar to software structure, only further up the stack.

The second reason is commercial. Model vendors do not want to sell tokens forever and stop there. As the base layer improves, they have every reason to move toward higher-value positions, own more of the user relationship, and sit closer to the workflow. You can already see this in product direction. Model vendors are not just offering APIs. They are building chat entry points, browser agents, coding agents, and office integrations. If your company exists to patch over current model weaknesses, you are standing in the path of the people who are most motivated to erase those weaknesses.

That is why this trend feels painful. It is not only a story about who built better software. It is also a story about where value was sitting in the first place.

## What gets absorbed first

Saying "the middle layer is dead" is too crude to be useful. Some kinds of middle layers are much more exposed than others.

The first exposed category is anything whose value depends on tuning around a specific model generation. A stronger model arrives, and the old prompt patterns, context packing tricks, and orchestration logic lose value fast. They are not worthless. Their half-life is short.

The second category is code that simulates abilities the model will likely learn on its own. General agent orchestration falls into this bucket. So do generic chat wrappers and thin workflow glue layers. You can spend months building them, and then a model update turns the core behavior into something native.

The third category is any product that still sits one layer away from a real-world loop. If it has no proprietary data, no distribution, no workflow ownership, and no responsibility boundary, then the product often comes down to one claim: we package the model a little better. That is the most fragile place to stand, because a model vendor only needs to take one step down the stack to make your difference feel thin.

LangChain is a useful case study. Its early importance was real. It helped people work through a phase when models were too weak and too inconsistent to be useful on their own. The problem was structural. It occupied a transitional layer. As models absorbed more of the planning and tool-use logic, the external orchestration layer became less central. Many agent startups ran into the same wall. They solved things the model could not yet do, not things the model would still need someone else to own after it improved.

The AI IDE market shows the same pressure. At first, the competition was about better completion, better context feeding, and tighter chat integration. Then users started to care about repository-wide understanding, multi-file edits, and control over the change boundary. Then the next shift arrived: model vendors shipping coding agents themselves. At that point the question changed again. Who owns the workflow? That is the real fight now. Cursor and similar tools are not forced to disappear, but they are forced to prove they control more than a convenient interface on top of a model. They need to own pace, review, safety, team collaboration, and the control surface around the work.

## What stays tied to the real world

Models absorb general-purpose capability. They do not absorb the real-world interface around that capability.

The durable pieces tend to cluster in three places.

### Workflow and domain constraints

A model, no matter how strong, does not show up with your company’s internal process, your medical compliance chain, your financial control rules, or the working habits a team has built over years. Someone has to connect the model to those environments.

That is where a lot of real value sits. The hard problem is rarely "Can AI do this?" The harder problem is "What is AI allowed to do here? Under which rules? Who checks the result? What happens if it fails?"

Take software development. "AI writes code" is not a moat. "AI operates inside a real engineering process, reads the right repositories, uses the right permissions, requires the right approvals, and triggers the right rollback paths" is a different thing. The hard part there is not generation. It is environment access, boundary design, and responsibility.

The same pattern holds in medicine, law, and finance. The hard part is not getting a model to answer. The hard part is getting it to work inside a system that can tolerate its presence. Can it touch patient records? Can it rewrite contract language? Can it participate in investment research? Each question opens into workflow rules, audit requirements, liability, and human sign-off. The deeper those constraints go, the less likely a generic model product can take the position directly.

### Closed-loop data and trust

When people talk about data moats, they often picture static corpora. That is not the strongest version of the idea. The stronger asset is closed-loop data: feedback that accumulates inside a live process, permission structures inside a business system, and relationships where users keep handing you more of the job because they trust you.

An AI speech coach is a good example. The real value may not be the critique itself. It may be the learning trajectory over time, the mistakes users repeat, the kinds of feedback that lead to improvement, and the relationship between practice patterns and actual progress. Once you build that loop, a better model increases the value of what you already own. It makes the coaching sharper, but the asset is still the loop.

The same logic applies in professional services. A law firm, consulting group, or enterprise service team rarely wins because it has the fanciest prompts. It wins because it has customer relationships, internal judgment, old case material, domain-specific standards, and accumulated trust. Models can make those assets run faster. The vendor still does not own the assets themselves.

### Task definition and accountability

A model can generate an answer. That does not mean it defines the goal. A model can execute steps. That does not mean it owns the consequences. Someone still decides what is worth doing, what level of risk is acceptable, what counts as done, and who signs off.

This point sounds less technical, which is exactly why people underestimate it. As long as real systems still need signatures, responsibility, and auditability, the model remains part of an execution system. It does not become the final accountable subject.

This is also why I do not think the question "Will AI become the true subject?" can be answered with capability alone. AI can write more of the code. It can draft more of the documents. It can produce the first pass of more analysis. That still leaves target setting, quality judgment, and responsibility in human hands. Capability is moving. Control and liability are not moving at the same speed.

## Engineering does not go away

A lot of people watch agent frameworks lose weight and jump to the wrong conclusion. They assume software engineering itself is fading. That is a dangerous mistake.

What fades is the decorative layer built to compensate for weaker models. What remains is the deterministic system underneath: evaluation, permissions, state handling, rollback, audit, and every place where one bad step can cause damage.

A model can be smart and still fail inside a constrained task. If a number has to match the database, it has to match. If an action needs a trace, the trace has to exist. If an external call fails, the system has to recover. If a code change goes live, someone needs to approve it first. None of those requirements disappear because the model sounds convincing.

That is why production conversations look different from demo conversations. Once teams put models into real systems, they spend less time on magic and more time on evals, sandboxing, observability, recovery, and layered checks. That is not a retreat from ambition. It is what happens when software meets consequences.

Prompt engineering theater is receding. Core engineering is not.

## Software will split into two layers

This is the direction I trust most right now. Software will not become "for AI" or "for humans." It will split more clearly between the two.

The lower layer will increasingly face the model. Interfaces will get more structured. Tools will get more programmable. Documentation will look more like capability descriptions. System state will become easier for models to inspect. Protocols like MCP matter because they solve a new kind of problem: they are not about making clicking easier for a human. They are about making system use more reliable for a model.

You can already see teams drifting that way. Function names get plainer. Module boundaries get cleaner. READMEs matter more. Command-line interfaces get more disciplined. Error output gets more structured. On the surface, that looks like maintainability work. It is also AI readability work. In many teams, the new reader is not only another engineer. It is also a model.

The upper layer still faces people, but the emphasis changes. Older interfaces focused on operation. The next wave will focus more on supervision. A person may not execute every step, but the person still needs to understand what the model did, why it did it, where the risk sits, and whether the result can be approved.

That is why I do not buy the simple line that software will soon be written for AI instead of people. A better version is this: lower layers will grow more legible to AI, and upper layers will grow more useful for human review and responsibility. The stack is being redistributed, not flipped.

## A simple test for where you stand

There is a harsh but practical question you can ask about any product or any career bet.

If a model ten times stronger arrived tomorrow, what would happen to the thing you are building?

If your product becomes more valuable because the stronger model can use your proprietary data, fit deeper into your workflow, or serve your customers better, then you are probably standing in the right place. Internal process ownership, closed-loop industry data, and long-term customer relationships all get amplified when the underlying model improves.

If your product starts to look unnecessary because users can go straight to the model vendor, then you are still living in the "patch the model’s current weakness" layer. You may have built something impressive. You are still building scaffolding for a temporary phase.

That test matters because it separates engineering volume from long-term asset ownership. The first can be large. The second can be small and still decide everything. What tends to survive is not the amount of glue code you wrote. It is the thing you control that somebody else cannot take with one product update.

You can put it more bluntly. Stop asking only whether a category is hot. Stop asking only whether a product has users now. Ask what happens when model vendors lift the base layer again. Do you get compressed, or do you get amplified?

The earlier you answer that, the less time you lose.

## The human role shifts, but it does not disappear

The deepest version of the current anxiety has little to do with one startup or one tool. It comes from the fear that once base capability rises fast enough, human effort stops compounding.

I do not think that is true. I do think the condition changed.

If you keep proving that you can do things the model already does well, the return on that effort will keep falling. If you connect the model to real workflows, build closed loops, hold the entry point, define the task, and own the consequence, the return can rise.

AI competition is moving from capability competition to position competition.

That is the question underneath all of this. Not whether the model replaces you. Whether each jump in model capability makes your position thinner or stronger.

Stand next to the model and sell the temporary patch for its current weakness, and it will catch you.

Stand on the real-world side of the system, where process, data, trust, responsibility, and distribution live, and every model upgrade can raise your value instead of shrinking it.

That is the coldest and most useful judgment I can make about this cycle. The noise will keep changing. The position will not.
