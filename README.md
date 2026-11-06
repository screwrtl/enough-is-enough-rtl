![Enough Is Enough: RTL](./assets/Enough%20Is%20Enough.webp)

<div align="center">

# Enough Is Enough: RTL

<sub>On the difference between supporting Persian and performing support for Persian.</sub>

</div>

Somewhere tonight a repository is being created. Its name contains `rtl`. Its README is longer than its source code. It has a screenshot of a dashboard with Persian labels, a confident line about being "fully RTL ready", and an empty issue tracker, which says less about quality than about traffic.

We have nothing against that dashboard. We have a problem with the queue behind it.

This is a protest by Iranian developers who want RTL to work, and who are tired of watching a real engineering problem become an endless supply of small, attractive, unused projects.

## TL;DR

> - RTL is broken in real products. That part is not a joke.
> - A mirrored landing page is a screenshot of RTL support, not a version of it.
> - We are not against RTL, Persian, beginners, or AI tools.
> - We are against performative engineering in an internationalization costume.
> - Build the difficult part. The easy part has been built badly, many times.
> - Fix upstream. The rest of this document is argument, context, and jokes at the expense of people who are probably us.

> **Acknowledgment.** This project owes its tone to [@yappologistic](https://github.com/yappologistic/), whose direct way of saying unwelcome things made this one easier to write. That is the entire connection: inspiration, not endorsement, affiliation, or collaboration. Nothing here should be attributed to them.

## The search that never ends

Search for a specific RTL problem, the kind that eats an afternoon. A caret landing on the wrong side of a phone number. A full stop that will not stay with its sentence. A table that is correct in the DOM and wrong on screen. This is not a survey. It is a frustration familiar to people working on Persian-language interfaces.

You will find answers. Very few of them will be about your problem.

You will find a beautiful README, a live demo, a feature list, and no tests. A starter that sets `dir="rtl"` on `<body>` and calls the layout finished. A library that solves mirroring with `transform: scaleX(-1)`, which is the layout equivalent of fixing a translation by mirroring the paper. The same demo, in the same framework, in different months, each one introducing itself as the missing piece.

What you will rarely find is the issue thread where somebody reproduced the bug, proposed a fix, and got it merged.

That absence is the subject here. Not the number of RTL projects, but their shape: wide, shallow, and disconnected from anything in production.

## We are Iranian too

This is the part that gets deliberately misread, so: we are Iranian developers. We write Persian daily. We know what happens when a support form rejects a valid Iranian phone number, a receipt prints a price backwards, or a search box fails on a name that uses a different yeh. We know why this matters.

Persian deserves correct shaping, direction, numbers, calendars, and interfaces that do not treat a right-to-left language as a styling preference. We respect the people building for their own language at night, unpaid, with nobody upstream listening.

That respect is why we are annoyed. A language with this much literature and this much accumulated frustration is not served by demonstration projects. It is served by interventions in software people actually use.

> Have some pride in Persian. Absolutely. But please, enough.

## The RTL Repository Industrial Complex

The pattern, which we have all watched and some of us have performed:

1. You get an AI agent, a long weekend, or a portfolio deadline.
2. You need a project, so you pick whatever interface was already open in a tab.
3. Persian labels go into the translation file, `dir="rtl"` goes somewhere, a font gets swapped, three paddings get moved by hand.
4. The README is written with confidence the code has not earned: "production-ready", "complete RTL support", "built for Persian developers".
5. The demo is deployed, the screenshot is taken, the post is published.
6. Commit history: `initial commit`, `add fa locale`, `fix rtl`, `update README`. Four commits, one of which is the README twice.

The demo is a settings page. The settings page is in Persian. None of the settings do anything. Installation means cloning the repository, because there is no package on any registry, which is one way to avoid ever answering a question about versions. The roadmap lists "RTL tests" under future work, next to a checkbox that has been unchecked for two years.

Not every RTL repository was built this way. Some are careful, and you can spot them in thirty seconds because they link to their tests and to the upstream issue they were written to solve. The rest are a genre, and the genre has conventions: dark mode usually reaching the feature grid before accessibility, RTL demonstrated by a navbar moving right, and everything difficult kept out of frame, including the user who types Persian into a field designed for English.

We asked for RTL support and received an ecosystem of RTL demos. That is a remarkable amount of effort aimed at the part of the problem a single CSS property appears to solve.

## Why another repository is rarely the answer

Even when the work is real, another repository is often the wrong delivery mechanism.

- **Fragmentation.** Twelve projects that each solve a fifth of the problem are twelve decisions a newcomer must make before writing code, and eleven of them are wrong for their case.
- **Maintenance debt.** A new repository is a promise about the next three years. Side projects can lose their maintainers long before their code stops being copied, and abandoned RTL code can be worse than none: the next person discovers its limits by shipping it.
- **Discoverability.** Search rewards projects that are good at being found, not good. Five confident READMEs later, the maintainer still has no fix and no afternoon.
- **Duplicated effort.** Every hour rebuilding a mirrored sidebar is an hour not spent on the parts nobody has solved.
- **No upstream improvement.** Patch the broken date picker in your app and you fix one screen. Land the same fix in the library and you fix every product it serves. The local patch feels faster; an upstream fix can help far more users over time.

None of this forbids new projects. It means a new project needs a reason stronger than wanting to build one, and that reason should be visible in the repository.

## The agent did not do this to you

Blaming AI coding agents for this is fashionable and lazy.

An agent will produce a Persian version of any interface you describe, with a README that reads like it passed review. That is the job. The output is fast, plausible, and structurally identical to the last one, because it learned from the last one.

The problem arrives the moment after generation, when a plausible artifact is mistaken for a finished one.

An agent can produce a working build in minutes. It can also search for prior art, read the library you are about to duplicate, and suggest that the work belongs upstream instead of in a new repository. All of that is useful. None of it is a verdict. It can even help test the form against a phone number, an email, and a Persian sentence. But a generated test result is no substitute for verifying real behavior with real keyboards and browsers. Whether the feature is implemented well is still your problem, and it stays your problem after the pull request is merged.

That judgment is the job. It always was.

So use the agent, generate the scaffold, and then take responsibility for the result: verify the claims, test the ugly cases, read the diff, check what already exists. Your agent survived the build. Your users still cannot type a phone number.

## There are other things to build

If the real goal is a portfolio, we have good news: we have never met the employer who was impressed by a mirrored dashboard. They tend to be impressed by software that does something difficult and does it reliably.

- A bidi-aware editor where caret, selection, and inline formatting survive a paragraph that changes direction three times.

- A Jalali date picker with real keyboard navigation, timezone handling, and a documented mapping to whatever the API stores.

- Server-side PDF and report generation with correct Arabic shaping, still broken in more products than anyone admits.

- A test corpus and fuzzer for bidirectional form input, so the next developer does not rediscover the same six edge cases.

- Accessibility work on a Persian interface people actually use, with a screen reader, on a real device.

All of it tackles harder problems than the demos we are complaining about. That is the point: meaningful work makes a stronger portfolio than another mirrored screenshot.

## The One Iranian, One RTL Repository Program

We propose a policy.

**Article 1.** Every Iranian developer is entitled to exactly one RTL repository. Name it well and keep it as long as it is useful.

**Article 2.** The entitlement is non-transferable, except to a relative learning React, where it is encouraged. Registration will be handled by a body we have not founded, using a spreadsheet we will abandon.

**Article 3.** A second RTL repository requires written permission from a person who has read the first one end to end. Attendance at the reading is not required. The reading is the policy.

**Article 4.** The "RTL ready" designation is earned by surviving one form containing a phone number, a price, an email, and a sentence that mixes Persian with English. Screenshots are not evidence.

**Article 5.** Anyone who fixes an upstream bug is exempt and may build as many repositories as they like, having already paid the tax.

We are not serious about the program. We are serious about the mismatch behind the joke: another personal RTL repository is easy to announce; reproducing, testing, and fixing an upstream bug is harder. We could use more of the latter.

## What actual RTL engineering looks like

This section is long because the work is long. It is the part the demos skip.

### The algorithm decides the order, not you

The Unicode Bidirectional Algorithm (UAX #9) defines how mixed-direction text is displayed. You will almost never implement it. You will spend years on its consequences: base direction and `dir`, `unicode-bidi: isolate`, the `<bdi>` element, LTR containers holding RTL runs, and the handling of mirrored brackets and parentheses, and the fact that quotation marks and other punctuation do not all behave the same way.

### Mixed content is where the bugs live

A realistic Persian sentence contains a product name, a year, a quantity, and a currency. Put "شرکت Apple در سال 2024 حدود ۳۹۱ میلیارد دلار درآمد داشت." on a page and watch the full stop, which takes its direction from the paragraph and settles somewhere you did not choose. Brackets around a Latin acronym mirror, correctly, and still look wrong. None of this is a browser defect. It is the algorithm doing its job on text nobody designed for.

### Logical properties, not a second stylesheet

Logical properties describe relationships instead of sides. `margin-inline-start` is the margin on the inline-start edge: left in a left-to-right paragraph, right in a right-to-left one. `inset-inline-start`, `border-start-start-radius`, `text-align: start`, and `float: inline-start` follow the same logic, and none of them is a drop-in synonym for the physical version. A rule that means the leading edge should say so and mirror itself. A rule that means the physical left should stay physical, with a comment explaining why the design is asymmetrical on purpose.

Where the intent fits, replacing physical rules is how you stop writing everything twice, and how you avoid a `[dir="rtl"]` block that has grown to four hundred lines. Tailwind, for instance, ships `ms-*`, `pe-*`, `start-*`, and `end-*`; the `rtl:` variant is a patch, not a strategy.

Then there is behavior that properties do not fix: chevrons pointing the wrong way, back arrows pointing forward, breadcrumbs in reverse order, chart axes and tooltips, carousels, sliders whose arrow keys were never told the layout mirrored. And `transform: scaleX(-1)` on a container, which mirrors the text inside along with everything else and is the fastest known way to be corrected in a code review.

### Inputs, carets, and the phone number test

Type `+98 912 000 0000` into the field labeled شماره موبایل. You have just created a bidirectional string in a field whose direction was chosen by someone thinking about something else. The caret now moves in ways your team will call "a Chrome bug". It is the field's direction, the algorithm, and the keyboard reaching a disagreement.

`dir="auto"` takes direction from the first strong directional character and skips digits, punctuation, and spaces while it looks. For names and free text that is usually what you want, and its failures are predictable. A field holding only digits has no strong character for the heuristic to use; the fallback depends on the element and its context. A Persian sentence that opens with a Latin product name may resolve to LTR, even if most of the sentence is Persian. And an editable field can change its direction as the user types, which is as pleasant as it sounds. Direction is a decision about content, so make it per field. `dir="ltr"` is a workable default for phone numbers, emails, URLs, IBANs, and license keys; free text can use `dir="auto"`; and one shared component means nobody decides differently on a Tuesday.

Persian keyboard layouts usually produce Persian digits, and `parseInt("۰۹۱۲")` returns `NaN`, which makes your validation message accurate and useless. Normalize at the boundary.

Then there are the characters that look identical and are not: Persian yeh (U+06CC) and kaf (U+06A9) against Arabic yeh (U+064A) and kaf (U+0643). Same shapes to the eye, different code points to every comparison, sort, and unique index you own. The user types their name correctly, search returns nothing, and the bug report says search is broken for their name, and they are right.

### The half-space is not decoration

ZWNJ (U+200C) is part of Persian orthography, not mere decoration. It can change glyph shaping, word formation, line breaking, and exact string matching. Search needs an intentional normalization strategy: blindly ignoring ZWNJ can conflate distinct spellings, while treating every variation as unrelated can hide legitimate matches. A project claiming robust Persian support should have thought about both.

### Numbers, dates, and the calendar you forgot

`Intl.NumberFormat('fa-IR')` commonly renders Persian digits by default; `fa-IR-u-nu-latn` requests Latin digits for localized display. Neither format should be mistaken for an API-safe numeric representation. `Intl.DateTimeFormat('fa-IR')` commonly uses the Persian calendar in environments with appropriate internationalization data, which may be what users expect on screen but is not necessarily what your database stores.

Two failures follow reliably. Localized display values get posted back and parsed as numbers or dates, which works until it does not. And date pickers get keyboard navigation built for a Gregorian grid, with months that move the wrong way and a "today" button that lies.

### Accessibility is not a later ticket

Start with `<html lang="fa" dir="rtl">` so assistive technology knows the language before the first word. Add inline `lang` on English fragments so a screen reader does not pronounce an API endpoint as poetry. Check that focus order still matches what the eye sees after mirroring. Then test with an actual screen reader: announcement order for mixed-direction strings can differ between platforms, so "it read fine for me" is a data point, not a result.

### Frameworks will not save you

If you render on the server, set direction there, or the first paint can arrive left-to-right before the client corrects it. Decide direction in one place and pass it down; component-level `direction: rtl` rules fight the document and each other. Most translation libraries translate strings. They do not mirror icons or lay out a page, which is how a project ends up with a complete Persian translation and a sidebar in the wrong place.

### Regression tests, or it is a screenshot

If you implement bidi logic, the Unicode conformance data (BidiTest.txt, BidiCharacterTest.txt) exists and will find what you missed. For everything else, keep a corpus of strings that break software: trailing punctuation, brackets around Latin acronyms, a phone number, an inline URL inside a Persian sentence, a price with a currency symbol, inline code in a paragraph, an emoji sitting on a direction boundary. Render each in both directions, in your supported browsers, at real widths, then look at the images, because the DOM will report a correct layout while the paragraph reads wrong.

### Maintenance is the deliverable

Browsers change, frameworks rename things, fonts ship new metrics, and each event can break a layout in a way your tests did not cover. The only defense is a person still paying attention. "RTL ready" is a claim about the next three years; a recorded demo is a claim about last Tuesday.

## What we are not saying

We are not saying Persian does not deserve first-class support. It does, and it does not have it yet.

We are not saying RTL bugs are trivial. They are difficult, which is why a flipped flexbox presented as a solution insults the people doing the difficult part.

We are not saying Iranian developers should contribute less. We are asking them to contribute where the contribution lands.

We are not saying AI tools are harmful. Unverified output is harmful, whatever produced it.

We are not saying all RTL libraries are worthless. Some are excellent. This repository links to none of them, which is a different problem you are welcome to fix.

We are saying the default drifted. "Build something for Persian" became "build a Persian version of something", and those are not the same sentence.

## Before you publish another RTL project

Answer honestly. Nobody is watching.

- [ ] Did you search for existing solutions, and can you name what they do and where they stop?
- [ ] Does the README's claim match the code, or does "RTL ready" mean the labels are Persian?
- [ ] Does a form survive a phone number, an email, a price, and a mixed Persian-English sentence?
- [ ] Does it work when direction is set per string, not only per page?
- [ ] Does it handle ZWNJ, Persian digits, and Jalali dates, or say clearly that it does not?
- [ ] Are there tests, and do they contain anything more interesting than a translated heading?
- [ ] Did you file the upstream issue before deciding to fork the world?
- [ ] Can anyone install it from a registry, and will you still be maintaining it in six months?
- [ ] Have you tried it with a Persian keyboard and a screen reader, on a device that is not your laptop?
- [ ] Would you ship it at work? If not, say so, call it a learning project, and save everyone a search.

## Better alternatives

**Fix the library you already use.** The bug is in a component you installed. Send the patch. The maintainer may be tired and insistent on a test you have never written. Write it; the fix then reaches every application using that component instead of one screen in yours.

**Turn the bug into a reproducible case.** One page, one broken input, one description of what happens in which browser. More valuable than most component libraries, and impossible to argue with.

**Write the documentation that does not exist.** Not a tutorial about setting `dir="rtl"`. A precise account of what happens, verified in two browsers, with the workarounds and what they cost.

**Build the unsolved part.** A bidi-safe editor, a Jalali picker with working keyboard semantics, RTL-correct server-side PDFs, Persian-aware search normalization, charts that mirror without flipping. Real gaps, still open.

**Improve a real application.** The Persian interface of something people already use. Not a demo of a product. A product.

**Collaborate instead of publishing.** Two people maintaining one good RTL library beats two people maintaining one demo each. The ecosystem does not need more front doors; it needs more rooms.

## FAQ

**Isn't this just another repository about RTL?**

Yes, and we are not going to pretend otherwise. The difference is that this is not posing as a library, a framework, or a starter. It is an argument with no dependencies, it will never be installed, and its only value is that you might read it before opening a new repository. If we are wrong, the right response is an issue on this one, not a new project.

**Aren't you being elitist about other people's work?**

We are being specific about a habit: publishing shallow work with grand claims. Beginners write small projects; everyone does, and they should. The problem is packaging that tells a beginner their first mirrored layout is ecosystem infrastructure, and tells everyone else to adopt it.

**You are Iranian. Isn't this self-hatred?**

It is the opposite. It is the belief that our language deserves work which survives contact with production. The soft bigotry is the version where a mirrored demo counts as support and everyone claps.

**Do you think RTL bugs are trivial?**

No. That is why the longest section here is technical. Our complaint is that the difficulty gets skipped, not that it is imaginary.

**Do you hate AI coding tools?**

We hate unverified claims. Tools do not make claims; people do. If an agent generated it, you still own it, including the parts you did not read.

**What if my project is genuinely useful?**

Then this is not about you, and you will know, because someone other than you has opened an issue and someone other than your mother has starred it.

**Would you rather nobody built anything?**

We would rather fewer people built the same thing. There is a difference between stop building and stop rebuilding. One is despair. The other is engineering.

## What Saber Rastikerdar Left Us

Persian interfaces need legible, well-designed typefaces. Saber Rastikerdar helped raise the standard for how Persian text looks on screens, sharing his work openly and freely.

Saber Rastikerdar ([@rastikerdar](https://github.com/rastikerdar)) made Persian typefaces Iranian developers have quietly relied on for years. Vazir helped change what a Persian interface could look like, and [Vazirmatn](https://github.com/rastikerdar/vazirmatn) carried that work forward with variable-font support, multiple weights, and the SIL Open Font License. His other families did the same in smaller ways: they made Persian stop reading like an afterthought.

He developed and shared his work in the open, creating something other developers could genuinely build on. That kind of lasting contribution deserves more than a passing mention.

While we argue about how many RTL repositories the world needs, he showed what meaningful work for Persian looks like: built, shared, maintained, left behind for people he would never meet.

**Rest in Peace, Saber Rastikerdar. Your work lives on.**

## The last word

The next time you create a repository with `rtl` in the name, pause for one commit message and ask what it will do that the previous ones did not. If the honest answer is "it will be mine", that is a fine reason to build something and a poor reason to publish infrastructure.

The problem is real. The overkill is real too, and it is easier to produce, which is why it keeps winning.

Every Iranian developer deserves a project. Not every project needs to be about RTL, and not every RTL project needs to exist. The next hundred hours of RTL enthusiasm would do more good as one maintained library, ten honest upstream patches, and a test suite that finally catches the full stop.

Have some pride in Persian. Absolutely. But please, enough.
