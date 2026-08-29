# Hi, I'm Saksham

Engineer. I don't have one specialty so much as a habit of following whatever's currently annoying me until I understand it — which has meant ML models one year, Linux internals the next, and a trace pipeline after that.

The stuff below isn't a portfolio with a theme. It's just what I got interested in.

📫 sakshamsrivastava0000@gmail.com · ✍️ [medium.com/@saksh-am](https://medium.com/@saksh-am) · 💼 [LinkedIn](https://linkedin.com/in/s-aksh)

## A paper

**[Investigating Cultural Bias: A Comparative Study of Large Language Models](https://doi.org/10.1007/978-3-032-18477-1_45)**
with Pooja Singh, Sonia Khetarpaul and Unnat Sharma — *PReMI 2025*, Springer LNCS

We wanted to know how much a model's output shifts when you change only who it thinks it's talking about. Two tests: **The Life of X**, which swaps identity markers like names and watches the story change, and **RECAP**, which asks for culturally-specific recommendations and grades the answers by hand and by machine. GPT-4, Gemini and Claude all drift the same way — they default to Western norms unless you tell them not to.

## Some things I've built

**[otel-pattern-sampler](https://github.com/sakshitposting-irl/otel-pattern-sampler)** — an OpenTelemetry Java agent extension that drops a noisy root span by name before it's recorded or exported. One span pattern was flooding a trace backend and the only options were to turn down sampling everywhere or go edit the app, so I made a third one. Java, no changes to the instrumented service.

**[summarize-for-noobs](https://github.com/sakshitposting-irl/summarize-for-noobs)** — a text summarizer on Streamlit that pulls out the parts worth reading.

**[Othello-AI](https://github.com/sakshitposting-irl/Othello-AI)** — agents playing Reversi at each other.

**[torch-mnist](https://github.com/sakshitposting-irl/torch-mnist)** and **[fmnist-torch-cnn](https://github.com/sakshitposting-irl/fmnist-torch-cnn)** — PyTorch from back when I was learning it. Left up on purpose.

Plus a [Java text editor](https://github.com/sakshitposting-irl/Java-text-editor) and a long tail of other repos, most of which exist because I wanted to see if I could.

## Writing

I have a thing on Medium where I take something I use every day and follow it all the way down:

- *Process Isolation: Linux Namespaces & cgroups*
- *What Happens When: Linux boots from power to systemd*
- *What Happens When: You Hit A URL*
- *Context Switch: The Illusion of Continuity*

Before those it was mostly ML — transformers, GANs, word embeddings, a bit of RL.
