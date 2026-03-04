---
layout: docs
doc_title: Transferring Data Using Globus
permalink: /documentation/getting-started/globus/
---

Marlowe has a Globus DTN that can be accessed via the [Globus web UI](https://app.globus.org). You will need to sign in to Globus with your Stanford SUNet.

## Globus shares

You can transfer data directly through Globus to three shares: `/scratch/`, `/projects/`, and `$HOME`.

All three are selectable as collections in the Globus file manager.

**New to Globus? Check out the official Stanford docs:** [here](https://globus.stanford.edu/)


## I can't see my /projects/ folder in Globus

Just like in the terminal, `/projects/` is mounted only as needed (an explanation is in the [FAQ]({{ '/documentation/faq/' | relative_url }}#i-cant-see-my-project-directory)).

To get your `/projects/` directory to show up, select the "Marlowe /projects directories" Globus collection, then manually type in your project ID *after* the slash.

Here's an example:

![walkthrough of finding projects directory in Globus]({{ '/assets/images/docs/globus.gif' | relative_url }})
