# Incubators (or: How to make large changes)

When proposing large additions to the core framework, using PRs is not ideal because integrating a PR into master 
is an all-or-nothing decision - the bigger the addition, the more it would benefit from real-world testing before 
integrating. OTOH it's difficult to get real world testing because testers have to switch to using the PR's branch 
(which is really hard if testers also need to use their own fork of the framework, or more than one feature under 
development), plus logistical difficulties such as the branch needs to be constantly rebased.

This puts pressure on the core-team to accept a PR before it is fully tested, and subsequent changes for improvements or 
bug fixes require a round trip of submission and approval by the whole core team each time; the newer a feature is, the 
more likely there are to be a need for "hotfixes" to solve urgent problems, which again is more pressure to accept changes 
without a proper review, and possibly a sign that the original review process wasn't good enough.

Incubators are a project-governance protocol for Qooxdoo projects, based loosely on Apache "Incubator" projects, where 
new additions to the core framework can be developed with a rapid code/test/review/release cycle and at the same time 
have the oversight of the core team, following our core principals of quality control and longevity.

Critically, Incubators are designed to make it easier and less work for the core team to review because a whole section 
of "core" new feature can be matured before final agreement to join the core.

The Incubator approach also allows substantial additions to be trialed without requiring the core team to approve via 
the core framework repo.  Incubators are a mechanism for saying "we think this is a good solution, but it needs to prove 
itself before we integrate it into the core".  This is similar to saying that the integration status of feature "X" is in 
alpha or beta, even if feature "X" is itself considered stable in its own right by a number of people.


## Incubator Libraries
New features can be presented as an "Incubator" project, which would be a repo inside the https://github.com/qooxdoo 
organisation and which would follow our normal rules for quality control (i.e. a PR/review/merge cycle, concerns for 
backwards compatibility, policy on documentation, etc) and longevity. The project becomes an official sub project, so 
we're putting commitment as a group into some kind of stewardship that may outlive the original developer's involvement 
(which is not to say that the project cannot be deprecated and retired, just that the life cycle goes beyond one person).

As an official project (especially one which is being considered for inclusion into the core framework) it would be 
normally sponsored by at least one core-team member (or at least, someone who is a strong candidate to become a core team 
member). And if it will use the `qx.*` namespace, there should be some discussion on which parts of the namespace it should occupy.


## Backwards Compatibility
As an official Incubator, the project would follow Qooxdoo guidelines for compatibility - EG freezing the API when we get to 
beta, or deprecating features in one version before removing them in the next, but this compatibility would be separate from 
that of the core framework.

For example, an Incubator could be compatible with Qooxdoo v6 and yet also take advantage of ES6 and therefore require the 
compiler (and therefore be incompatible with the generator).

Potentially, an Incubator could include an ES6->ES5 transpile as part of it's release process to produce a version especially 
for generator compatibility; but some transpiled code is very hard to read: async/await is translated into a state machine 
inside the function where it occurs. The decision to provide this or not is left the Incubator author.


## Naming Convention
It's useful to be able to identify repos with special "Incubator" status, and to do that the repo name would follow a naming 
convention that starts with "incubator." plus the namespace used by the new feature

For Incubators which are proposed as an addition to the core framework, and which use the qx.* namespace, this would mean
repo names such as  https://github.com/qooxdoo/incubator.qx.newfeature  where the classes are in the `qx.newfeature` namespace.
This makes it clear that it is an officially supported project or proposal, but the incubator status shows a certain flexibility 
and independent development stream from the core framework.


## Lifecycle
When one version of the Qooxdoo core framework is released and we're working towards the next, that would be a good point to 
consider whether an incubator is stable enough to incorporate into core.  The core team should maintain a road map for when 
the proposed new libraries are integrated into the core, ie Incubators are not allowed to languish at github, they have to 
have a specific destiny - of course this implies that if they don't make it, they get deprecated and then archived.

It is important to prevent https://github.com/qooxdoo from becoming a dumping ground of half finished repos, and most 
importantly prevent `qx.*` from being populated with code that's since fallen out of favour.  The timings and how it happened
are lost in history, but by way of example there always seems to have been a deprecated `qx.io.remote.*` in favour of `qx.io.request.*`.


## Merging into the core
When an Incubator is merged, the namespace of the code should not change - the intention is that user code will be able to
simply remove the repo and recompile with the latest framework and their app will work as normal.

For this to happen, the Incubator authors should endeavour to make sure that there will not be any breaking changes when 
integrating; this moment of integration is the cross over period from more relaxed rules and faster development cycle, to
the stricter rules of the core where backwards compatibility, stability, and longevity are crucial.  Inevitably, there
may well be times when this is perhaps not 100% possible during integration, and ultimately an Integration is a way of 
"beta testing" a new project, but part of the purpose of Incubators is to promote new projects to users outside of the core
team and stability is important.    


## Using the Incubator
Because the compiler supports dependencies it would be easy for anyone to incorporate Incubators into their development - if 
the Incubator is ES5 then the same can be achieved with the generator, albeit with some additional manual work to get it up 
and running.  But backwards compatibility with older versions of Qooxdoo is not a requirement, and so generator compatibility
is entirely optional and up to the author(s) of the project.


## Use Cases
There are two projects being developed at the time this document is written (2019) which have lead to this proposal; they are 
features which seem like a really good fit for Qooxdoo core and had a positive response; as they're both a large feature it made 
sense to develop it outside the core.

The complexity and multiple authors means that it will take some time for the code to mature, but there is also the more practical
problem of ES5/ES6 support. 

The code in the latest alpha version is getting fairly complex, and relies heavily on ES6 - not just nice-to-have syntactic 
sugar like arrow functions, but async/await handling is a huge improvement for asynchronous work, and in this case async is 
a very big part of the code.  Our stability commitment means that we have to support ES5 and the generator during Qooxdoo v6, 
and that means it would have to be translated into ES5.  Translating it into ES5 would be a lot of grind with the only value 
being backwards compatibility for the generator.

