# Writing a (light) program specification document (spec)

- live version (in Markdown) at https://github.com/ChHarding/planning-spec-example
- example sketch (Earth quake activity app): https://github.com/ChHarding/planning-spec-example/blob/master/sketch.md
- example planning spec for it: https://github.com/ChHarding/planning-spec-example/blob/master/How%20to%20write%20a%20light%20project%20spec.md


### What's a spec?
-  A document that lays out (in some detail) how the project should(!) work. This includes a user centered part (use cases, vignettes, etc.) but also a technical part. For bigger projects It also distributes work across a team (who works on what parts?) and lists milestones (what date? what deliverables?). For this light spec (for version 1 of your code) we'll skip milestones for now, but they will become rfelevant when you update your spec for version 2!
- there are many official, software engineering ways with rules for how to create a software spec. Example: https://blog.tara.ai/software-design-documents/ (Note: this is for a commecial product but it has a (to my mind) concise summary of the process and typical parts. Some of these are overkill for our purpuse, but still worth knowing about.


### How will we use the spec?
- You will write a light spec and I will give you feedback (HW)
- You will start working on a version 1 prototype of your project based on your spec (again, I'll give you feedback)
- It's likely that you will want to revise your spec based on your experience with version 1.
- Based on the revised spec, you will implement a version 2. This will now include milestones.


### Scope of a light spec
- You will NOT be required to produce such a full "proper" spec. My aim in having you write a __light__ spec is purely to force you "think through" many part of your project __before__ you dive in. 
- One major purpose of a "proper" spec, is to create a contract between the programmer(s) and their bosses/clients. That spec protects the programmer from any demands (or unfair criticisms) arising later. E.g. a client might complain that something is different than expected, and demand changes. With a proper spec, the programmer can go back and look what the spec demands. Granted there are grey areas in interpreting the specs, so it's good to be as precise as possible. 
- However, for your spec it's very likely that you will have to revise your spec after you've done some coding, which is fine!  Nobody expects you to write a perfect spec and stick to it on your first try!
- But, there's one aspect that you should try to keep an eye on: feature creep.


### Avoiding feature creep
- feature creep is the ad hoc, out-of-spec adding of functionality during the implementation of the spec. Either the client discovers new requirements, or the programmer realize that something cool "could be added easily"
- To be clear: any more/different things you think of while you're still writing the spec are fair game! Just resist the urge to tinker/improve you code right away during your implementation of version 1. Reality may/will force you to downscale or abandon planned featured, which is fine but don't get sidetracked! 
- If you discover that something nice/cool could be done add it as a __feature add/enhance request__ at the end of your spec and make a note how it could be done technically. Try to also jot down other helpful things: how big a job would this be? Would this require adding isolated new code or would it impact already existing code?  We will go over add/enhance requests in more detail during the review of version 1, where you will very likely end up writing them in much greater detail. Feature requests, together with bug fixes, will be a major part of updating your spec between implementing version 1 and version 2.


### Developing "multi-stage" features
- in your spec, you should try to articulate what a feature does. E.g. _Ability to add new users_
- If at all possible you should, at this stage, try to design multiple stages for this feature
    - minimal/core: what's the bare minimum that it must archive? This is the core, which should be your goal for version 1. (Ex: new user data will be entered by hand and stored locally)
    - additional layers: if you can already see more functionality, write it down but clearly flag it it as additional (i.e. NOT core). This could be additional ways to perform the same task (Ex: add new user data from a file, via email, via API call) which you may want to implement later


### Exploring if/how something is technically feasible 
- if possible, the spec should talk about __technicalities__ (at a high level!), such as datatypes, modules or APIs you may want to use.  
- If you can see a way to implement something with simple lists, dicts, loops, etc. - great! But, maybe you can already see that using a module will be easier,  e.g. maybe use pandas dataframes, instead of nested lists.
- You should use this spec phase to poke around and find packages or APIs that you could potentially use. If available, fork/clone/download the package and run the tutorial or create a __very simple__ example. You should be about 75% sure that you will be able to use it. Writing code experiments is fine but resist the temptation to dig in too deep and to already start with the implementation. 
- Put the results of your exploration into the spec and capture: a) what you already __know__ it can do (i.e. you tried it yourself already on a very small scale) and b) what you __think__ it can do (i.e. what reading about it on the project home page or on stack overflow seems to indicate)- Also add any caveats (seems complicated, not used by a lot of people, development abandoned, need X to work, requires free/pay dev license, etc.)
- Resources:
    - The HCI 584 Resources page on the canvas home page 
    - https://pypi.org/search/?q=&o=&c=Programming+Language+%3A%3A+Python+%3A%3A+3+%3A%3A+Only click on topic  

### How do I know what features I need?
- It's advised to work out the required features by looking at the needs of the user
- Note: there is a hole sector of HCI and software development that deals with user centered design https://en.wikipedia.org/wiki/User-centered_design  
- Although, running a full user centered design process is completely outside the scope of this course (for many reasons) we will try to incorporate a few elements, starting with looking at the user and defining tasks and requirements.  While it would be nice to interface with proper users, interview them, design personas, etc. we simply don't have time for this. 
- Instead we will assume that you are the user and describe the task flow in a series of vignettes. This may/will include assuming expertise that you don't have, which is OK! Again, the aim is to make you think through the tasks and write down something concrete, thereby hopefully giving you confidence in your plan or revealing that you need to rethink some parts!

## Deliverable parts for your "light" spec 
- As with the sketches, please hand in a pdf of your spec but also give me a link to a google that I can edit

### General description of the project (2 pts)
- start with your sketch and enhance it.
- The actual description (summary) should be about a half page (3 - 5 paragraphs) and initially introduce your project so that a non-techie (like your boss) can get the gist of the project. 
- Also:
    - Mention, if applicable, what external mechanisms (major packages, API, email, twitter, etc.) you will use
    - What GUI would it ideally use? Could it minimally run with a command line interface (CLI).
    - Could this also have a "remote" control, e.g. offer some form of API?


### Task Vignettes (User activity "flow") (4 pts)
- For each major task write a short vignette that illustrates it. Again, it's OK to just assume a lot of things ... like that your user really needs to perform a task (although you don't actually know that) or that the task will be for now performed magically (to be solved later).
- The order of your task should make sense. It's OK to bundle several tasks into a vignette if they are naturally related 
- I expect 1-2 paragraphs per vignette
- After each vignette, you should list technical details as bullet points. This includes anything that the user may not be aware of but that could be potentially important for the implementation.

- If you can, add crude design mockups or wire frames (hand drawn or simple power point diagrams) that capture the user interaction. You can re-use mockups created for the sketches. However, these are __not a must!__  For now just articulate what actions happen and what data flows where. 
- You don't have to design a GUI for the spec, although for many that's a natural way to articulate the activity. 
You're welcome to use it as a "graphical language". 
- Just know that for your version 1, you may actually end up implementing the data flow as a command line interface!


### Technical "flow" (3 pts)
- Now that you've described the user tasks and actions, you should look at the flow from a more technical side. Strictly speaking this goes deeper that a high-level spec would typically require, but I think it's a valuable exercise to go through before beginning to code!  
- I realize that this may be tricky for you ... as usual, just do your best, I will reward demonstrated effort. Example in:  https://github.com/ChHarding/planning-spec-example/blob/master/How%20to%20write%20a%20light%20project%20spec.md
- I find it best to think in terms of data flow (i.e. input/output) but if you know OOP and plan to use it, you might do a bit of early class design here instead. (There will be a lecture on OOP soon)
- Describe the overall “flow” of data, either with words (see example) and/or by creating a simple diagram on paper, with PowerPoint or with an online drawing app such as https://app.diagrams.net/ or https://draw.io Or  do it on paper and hand in a snapshot of it.

    - Jot down what blocks you think you’ll need and maybe try to group them into larger blocks.
    - Name the blocks by what they do (this will help with names for classes/functions/modules later!)
    - Use arrows to show which blocks need to generate/receive/exchange data (flow)
    - Separately jot down the types of the data in that flow (list, dictionary, array, compounds, classes?)
    - Note which blocks involve user interaction and of what kind (input? Output?)

### Final (self) assessment (1 pts)
- After working through the spec, what was the biggest most unexpected change to had to make from your sketch?
- How confident do you feel that you can implement the spec as it's written right now?
- What is the biggest potential problem that you NEED to solve (or you’ll fail)?
- What parts are you least familiar with and might need my help?

