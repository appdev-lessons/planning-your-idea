# Planning your idea

You started the quarter, we assume, having not written any software. Can you now identify a problem that can be solved with software and build something to test your theory?

The goal is for you to take a _proof of concept_ — which is smaller than a minimum viable product — from a sketch all the way through deployment, and thereby witness firsthand at least one cycle of software development, and its constituent moving parts.

That's a lot to do, so keep the functionality to a minimum — **keep it simple**.

## Requirements

### Hard requirements

- It should solve a problem that you clearly articulate.
- It should be interactive in some way; in other words, it should not just be an informational, static website. (Adding a "Contact Us" form to the bottom of a landing page is not sufficient interactivity.)

That's it. Due to the wide variety in the ideas that people come up with, those are the only hard requirements.

### Soft guidelines

However, historically, the vast majority of final projects (like the vast majority of software that we use on a daily basis) have also fit the following pattern:

- You can interact with it through your browser.
- It uses a database to store information.
- It has some associations (one-to-many and/or many-to-many) between tables.
- It has sign-in/sign-out functionality to personalize the experience for each visitor.

In other words, standard CRUD applications.

In very rare cases, an idea might not need a database (perhaps it reads and stores all data using an external API) or it might not need sign-in/sign-out (perhaps you are the only user and it emails you a CSV every morning). If you have an idea like this, you should run it by me. If it's not static HTML and it solves a problem for you, I'll likely be happy with it.

But, mostly, projects fit the pattern of standard CRUD applications; similar to the ones we've built together in class — to-do lists, social networks, two-sided markets, etc.

## Deliverables

Ultimately, you will submit:

1. **Screencast (required)**

    You will record a very brief (2-5 minute) screencast walking me through your application. Imagine that in the future some day you will interview for a position as a product manager, and this screencast will be your way of demonstrating that you rolled up your sleeves and learned how to code at one point.

    In the screencast, demonstrate the critical, unique flows in your application. You don't have to walk me through signing-up and signing-in as each user; those are not unique flows. It's usually helpful to pre-create some users and other sample data before starting your recording.

    You can use any recording method you like. You could record a Zoom call where you are the only participant and sharing your screen. [Screencastify](https://chrome.google.com/webstore/detail/screencastify-screen-vide/mmeijimgabbpbgpdklnllpncmdofkcpn/related?hl=en) is a free Chrome extension. Etc.

    Once recorded, upload the video file to YouTube, Dropbox, Google Drive, or whatever service you prefer; but whatever you choose, you must be able to share a link with us that does not require signing in. In other words, anyone with the link should be able to view the video. On YouTube, this is known as an Unlisted (not Private) video.

2. **A link to your GitHub repository (required)**

    **Make sure you make a commit of your latest work and push it to GitHub**. You can find your GitHub repository under your account on GitHub.

3. If you choose to deploy your application to Render, **it's production URL (optional)**. You need not put it behind a custom domain — `your-app.onrender.com` is fine.

    If deploying to Render is applicable to your idea, consider doing it! [It only takes takes a few more steps](https://learn.firstdraft.com/lessons/215-rails-on-render), but then your app will be on industrial-grade infrastructure for posterity, even if GitHub deletes your codespace for inactivity.

4. Would it be okay with you if we share your screencast with future students? Yes or no

## Getting started

1. Start with a blank Rails application by [creating a repository from our template](https://learn.firstdraft.com/lessons/236-rails-template).
2. Start your web server from the terminal after the setup completes. Open your app in a new tab and see the Rails default page.
3. Pick whichever URL you want your users to be able to visit first and type it in to the address bar. See the "No route matches" error message.
4. Make it work!
5. Rinse and repeat.
6. **A**lways **B**e **C**ommitting.

## Keep it simple

The first step towards implementing a full product is eliminating the biggest unknowns with small, experimental, _proofs of concept_. The big questions often include:

- Where is the required information coming from?
  - Are our users supplying it?
  - Is it available from an API?
  - Can we download a CSV from a government website?
  - Can we scrape a website for it?
- Is our domain model correct?
  - Did we identify all of the information we need to store to solve the problem?
  - Is our database architecture correct — i.e. are our tables and columns sufficient to store the information?
- Are we solving the right problem, or is an adjacent one more pressing?

We usually throw away the code from 3 or 4 of these small experiments before we build out anything resembling the first real product. So, again — **keep it simple**. Don't complicate the codebase by planning 6 months worth of features ahead. What's the smallest thing you can build right now that will allow you to test one assumption?

Chat with us during office hours to help select an idea (hopefully from among a handful) and scope it down to a good initial featureset.

---

## Read on for tips and advice

The above is the essential info. Read on for tips and advice.

### Ideation

Before we begin writing code, we want to have our complete domain model in hand:

- all tables
  - including any join tables required for many-to-many associations
- all columns on each table
  - including foreign keys required for one-to-many associations
  - the datatype of each column
  - any validation rules we want on each column

To get there, we of course need to first have an idea. And, for me, it helps to visually sketch out the screens in my app and the links between them — a "wireframe" — before I try to design the database architecture to back it.

Maybe you already have a clear idea of what you want to build. If so, great! Stop reading. If not, here are some resources I've found helpful for coming up with an idea and wireframing it.

### Pain Points

You should think of a couple of pain points in your life that you would like to solve with a simple CRUD app. Remember,

> The verb you want to be using with respect to startup ideas is not "think up" but "notice."
> — [Paul Graham, "How to Get Startup Ideas"](http://paulgraham.com/startupideas.html)

The essay that quote is from is a good read, but don't try to think up billion dollar startup ideas; our goal here is to discover a good first learning project, not to change the world just yet. Try to notice a real annoyance at work or at home or with friends that we can solve, even if for just one user — you.

For example,

- We've looked at a couple of student projects in the past.
- Many ideas involve improving the campus experience in some way.
- Many ideas involve improving living with roommates in some way.
- There are lots of two-sided markets that are still ripe for building. (Airbnb and Lyft are examples of two-sided markets, where ordinary people are both providers and consumers [of housing and transportation, respectively].)

The bottomline: keep it simple. It's best to think up more than one idea if you can, so that we have options to choose from.

### Sketches

Once I have an idea in mind, I immediately reach for pen and paper and start sketching. If you have your own process for wireframing, feel free to skip to the next section, [User Stories](#user-stories){:target="_self"}. Otherwise, read on.

#### Crazy Eights

I like to start with some [Speedy Eights](https://thoughtbot.com/product-design-sprint/guide/diverge/speedy-eights) to force myself to just get some thoughts down on paper.

I will usually do two or three rounds. One round, I'll use the 8 panels to progress through the different screens of a flow. Another round, I'll use the 8 panels to explore 8 different takes on the most important screen in the app.

Remember, you are only supposed to spend around 40 seconds per panel! Actually set a timer and stick to it. Try [using a sharpie rather than a pen](https://signalvnoise.com/posts/1788-oldie-but-goodie-sketching-with-a-sharpie) to prevent yourself from getting into too much detail in this phase.

#### Wireframe

Then, I select one flow that I like, and I draw out each screen in a bit more detail. I like the [Prototyping On Paper](https://marvelapp.com/pop/) app to connect the sketches of each screen together, and eventually I try to "crawl" from every link and button in each screen to every other screen until I've drawn out the entire app (excluding obvious things like edit profile forms).

### User Stories

Next, I list out all of the features that I've identified in my wireframe.

When I'm writing down a feature, I usually phrase it as a [User Story](http://www.romanpichler.com/blog/10-tips-writing-good-user-stories/). User stories are just features, phrased in a particular manner:

"As a **[role]**, I want to be able to **[capability]**," (and, optionally), "so that **[benefit]**."

The aim is to always be thinking from a user-centric perspective, and not from a technology or implementation perspective yet.

- First, brain-dump all the features you can possibly imagine as user stories.
- **Then, re-order them by priority.**
- Then, crucially, ask yourself: **what is the absolute minimum featureset I can get away with in this first experimental prototype?** The prototype's purpose is just to validate whether or not the idea is feasible and whether the core value is actually valuable. **Be ruthless in eliminating all non-essential user stories for this 1st draft.**
- Move **only the essential stories** to a new list: this will be your proof-of-concept featureset.

These proof-of-concept features are what you should try to design a domain model for. Don't plan ahead for anything else — you'll just create extra work for yourself, for likely no return. Remember that we will most likely throw away our first proof of concept and re-write it with our learnings.

Inevitably, as soon as you start programming, you'll think of different approaches, features, tables, or columns. Don't forget to **A**lways **B**e **C**ommitting. Then you'll never lose work; you can either jump back to reference old commits, or just start fresh from that point in time.

## Diagram your idea

[ideas.firstdraft.com](https://ideas.firstdraft.com) is a tool designed to help you plan out your app idea from an information-storage perspective.

### Domain Modeling

Now that we've identified the features we want to include in our experiment, it's finally time to start thinking about how we're actually going to code it up.

The primary thing we need to do is **identify the tables and columns** we need in our database to keep track of all the information required to support the user stories. This is known as **domain modeling**. If we can get this part right, the rest of the code practically writes itself (trust me, you'll see).

My process for domain modeling is, once I have my list of actions and information on each screen, and my user stories in front of me -- try to identify the important **nouns** in the app. These usually become tables -- for example, events, recipes, tweets, users, messages, etc.

For each table, try to identify the columns we need. What are all the attributes about that thing that you need to track? For example, for events, you probably need held_on (date), title (string), description (text), location (string), etc.

Start diagramming out your domain model in [ideas.firstdraft using our guide](https://learn.firstdraft.com/lessons/233-ideas-tool).

#### Associations

The last and most crucial step in domain modeling is identifying relationships between each pair of tables.

A relationship can be one of two types: one-to-many, and many-to-many.

For example, in Instagram, a photo can be associated to many comments, but a comment can only be associated to one photo. This is a one (photo) to many (comments) association.

On the other hand, in IMDB, a movie can be associated to many actors, and an actor can also be associated to many movies. This is a many-to-many association.

The first step is, try to go through all of your tables and identify all one-to-many associations.

Once you feel good about your one-to-manies, try to identify all the important many-to-manies too.

For all one-to-manies, decide which table should get the foreign key column, and what it should be called.

For all many-to-manies, decide on a name for the join model.

Add your associations, and any required join models and foreign keys, to your [diagram in firstdraft Ideas](https://ideas.firstdraft.com/).

**You should now have a complete listing of all your tables and columns, including those needed to support your associations.**

**Once you've taken a stab at writing down your domain model, it's time to book an appointment with one of us to review it.** The more progress you make on your own with domain modeling, the more productive our chat will be.

### Co-pilot

When you think you're ready to start coding, then consider [using the co-pilot feature on ideas.firstdraft.](https://learn.firstdraft.com/lessons/244-ideas-tool-copilot)

---
