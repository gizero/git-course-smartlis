# Source Code Management
## (with git)

### Andrea Galbusera

***

gizero@gmail.com

[@gizero76](https://twitter.com/gizero76)

https://github.com/gizero

Note: Good morning everyone, welcome to this course. I hope you'll enjoy the
time we'll spend together

---

# The Speaker

embedded systems designer/architect

spare time full-stack web developer

doing SCM since 2002 (in some way teaching it)

using `git` since 2010

continuously researching into SCM technologies and best practices

---

This presentation is available at:

http://gizero.github.io/git-course-smartlis/

Sources:

https://github.com/gizero/git-course-smartlis/

---

# Agenda

## Day 1
- disclaimer
- what's this all about?
- (brief) history of SCM
- workshop

---

# Disclaimers

- work in progress teaching experiment
<!-- .element: class="fragment" data-fragment-index="1" -->

- many concept are tool agnostic...
<!-- .element: class="fragment" data-fragment-index="2" -->

- ...but this is about `git`
<!-- .element: class="fragment" data-fragment-index="3" -->

- client agnostic
<!-- .element: class="fragment" data-fragment-index="4" -->

- ...but heavily biased towards command line
<!-- .element: class="fragment" data-fragment-index="5" -->

Note: git learning curve is often considered to be steep. My opinion is that the
tool should not be the main focus. Here we try to get into the git topic with a
teaching experiment... Hopefully things will become simpler and git command
details will be just a man page away from you.
Answers some of you provided to the preliminary questionaire will come handy for
tuning the way to teach of some course topics.

---

# In This Course We

- talk interactively to each other
- sketch some diagrams
- build some reasonable workflow strategies

Note: Wow, I thought this was about those cryptic git commands. Well, yes and
no. At least not right now. I need you to enter

---

# Then...

- you will learn the commands to implement them

Note: invece di concentrarsi sui comandi ci focalizzeremo maggiormente sul
perchè vogliamo fare qualcosa e poi su come implementarla. Useremo qualche
diagramma per stimolare gli stessi processi di apprendimento che normalmente
portano alcuni di noi a preferire le GUI rispetto alle interfacce CLI.

---

# Vocabulary

- Source Control
- Version Control
- Revision Control
- Source Code Management

Note: con il termine SCM comprendiamo anche pratiche e strumenti più o meno
correlati con il controllo di revisione, quali il deployment e il ticket/issue
tracking. Quindi vediamo cosa ci permettono di fare questi strumenti che rientrano
nella classificazione appena introdotta...

---

# What is version control

Note: Ask, “Who uses ‘undo’ in their editor?” All say “Me”. ‘Undo’ is the
simplest form of version control.
Give learners a five-minute overview of what version control does for them
before diving into the watch-and-do practicals. Most of them will have tried to
co-author papers by emailing files back and forth, or will have biked into the
office only to realize that the USB key with last night’s work is still on the
kitchen table. Instructors can also make jokes about directories with names like
“final version”, “final version revised”, “final version with reviewer three’s
corrections”, “really final version”, and, “come on this really has to be the
last version” to motivate version control as a better way to collaborate and as
a better way to back work up.

---

# With SCM tools we...

- keep track of changes over time
- backup older files
- work with others on a project simultaneously
- keep track of authorship
- deal with big (or even small) changes that break things
- move things from one host to another

Note: hosts can be either development, staging or production hosts. Supply chain
is intrinsically bound to how a change flows from the designer/developer mind
down to the production.
Version control is like an unlimited ‘undo’.
Version control also allows many people to work in parallel.

---

## In brief, this is all about

## managing the change

Note: mention cool concepts like "design for changeability", but most
importantly focus the audience to the unavoidable changing nature of their job
artifacts.

---

# working in team?

- don't step on each other's feet
- minimize coordination overhead
- reduce onboarding costs for new resources
- leverage and improve team skills with peer review

---

# working solo?

- productivity tool
- easily switch between tasks
  + parallelizing activities
- quickly react to urgencies
  + make a quick fix while working on a new feature

---

# Authorship

- keep track of "who made what"
- allow "blaming" changesets

---

# do I really need a tool? (alternatives)

Frequently backup your files (caveman's SCM)

- straightforward: anyone knows how to do it
- error prone (write to wrong dir)
- what does "frequently" mean?
- how to deal with backups (housekeeping)
- hard to find useful things among backups
- doesn't address the collaboration issue

Note: Does your boss really need to invest money on a tool? Can't we really
solve the same problems with ready made tools every computer can provide?

---

# Distributed vs Centralized

Note: if anyone of you have had previous experience with other SCM tools
before using git you probably read that those tools belong to two broad
categories...
Automated version control systems are nothing new. Tools like RCS, CVS, or
Subversion have been around since the early 1980s and are used by many large
companies. However, many of these are now becoming considered as legacy systems
due to various limitations in their capabilities. In particular, the more modern
systems, such as Git and Mercurial are distributed, meaning that they do not
need a centralized server to host the repository. These modern systems also
include powerful merging tools that make it possible for multiple authors to
work within the same files concurrently.


--->

# Centralized VCS

- there is only one repository every contributor connects to
- there is a single history of revisions
- easy to administer and manage access control
- single point of failure

--->

# Centralized VCS

- SVN
- TFS
- CVS

--->

# Distributed VCS

- every contributor mirrors the entire history
- every clone is a full backup

--->

# Distributed VCS

- git
- Mercurial
- BitKeeper
- Veracity

---

# So what is GitHub?

Note: try to clarify where git ends and GitHub and friends do begin

---

# Distributed == anarchy?

---

## Distributed as the New Centralized

![Centralised](assets/workflow-centralized.png)

--->

## Integration Manager

![Integration Manager](assets/workflow-integration-manager.png)

--->

## Dictator and Lieutenants

![Dictator and Lieutenants](assets/workflow-dictator.png)

---

# Exercise 1: outline your team

Who is in your team?

Note: dare un'idea di cosa vogliamo fare senza svelare i dettagli. Cerchiamo di
conoscere il team e il teamwork per caratterizzare i workflow di interesse.
Usiamo come riferimento un progetto reale che coinvolga un numero significativo
di persone oppure proviamo a immaginare un progetto imminente o anche fittizio
sul quale ragionare.

--->

# Exercise 1: outline your team

What are their roles?
+ developers
+ designers
+ project managers
+ clients

--->

# Exercise 1: outline your team

What task are they responsible for?
+ writing code
+ reviewing code
+ pushing code to servers
+ fixing broken code

Note: prendete carta e penna e scrivete i nomi delle persone coinvolte nel
progetto, indicando i loro ruoli e le attività delle quali sono responsabili:
utilizzando i verbi come download work, create snapshot, share work

--->

# Exercise 1: outline your team

What constraints are you dealing with?
+ how do you schedule your deadlines?
+ where is your code hosted?
+ do you have a staging instance?
+ where are the server you push to?
+ do you use a local development pattern?

Note: I tricked you and you just built a checklist of what you need to create a
workflow you can use with git

---
