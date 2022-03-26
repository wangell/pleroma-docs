# What is Pleroma?

And what the bleep do we know?

Pleroma is a distributed, object-oriented operating system/VM inspired by the original vision of Alan Kay's Smalltalk, the E programming language, and Plan9/Inferno.

The creator or creators of Pleroma are entirely unknown - it is a found operating system.  The specification was discovered in a cache located in Oxyrhynchus, Egypt dating back to the 3rd century.

Pleroma is the answer to the following questions/problems:

- What happened to Smalltalk?
- I want to host reliable internet services from multiple computers (some on my personal network, some on the cloud, some mobile), but Kuberenetes is too complex
- Distributed software always ends up becoming centralized due to reliability
- Why do I need Protobufs, API specs?
- I feel unsafe downloading/running code from Github without reading it first
- I have a lot of computing devices and no way to manage them uniformly
- I need concurrency without all of the baggage
- Actor systems are pointless without a strong distributed story
- I don't want to know, or care, about where my software is running
- Personal computing research has been completely stagnant, despite major technology advances in the last 50 years
- I think that E/Plan9 were ahead of their time and/or interesting but ultimately useless
- Using Erlang doesn't make me feel good inside, and I don't know why
- I want to host my own email, but due to a laundry list of problems, that's not possible
    
The four core components are:
- [Pleroma](./pleroma.md): the actual operating system
- [Hylic](./hylic.md): a statically-typed language
- [Allo](./allo.md): the communication tool for interacting with Pleroma
- [Charisma](./charisma.md): a novel IDE integrating voice and AST editing

Pleroma is versioned according to the solstices.  `w22` and `s22` referring to the winter and summer solstices of 2022, respectively.  Versions can't be patched unless there are major security issues, in which case one can append `p` and an incrementing number (e.g. `w22p4`).  Otherwise, a version is frozen in time and all new development takes place on the next solstice release.
