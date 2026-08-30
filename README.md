# Hi, I'm Saksham

No fixed specialty, I just work on whatever's annoying me at the time. That's been ML, then Linux internals, now tracing.

Not really a themed portfolio below, just stuff I got into.

📫 sakshamsrivastava0000@gmail.com · ✍️ [medium.com/@saksh-am](https://medium.com/@saksh-am) · 💼 [LinkedIn](https://linkedin.com/in/s-aksh)

## A paper

**[Investigating Cultural Bias: A Comparative Study of Large Language Models](https://doi.org/10.1007/978-3-032-18477-1_45)**
with Pooja Singh, Sonia Khetarpaul and Unnat Sharma — *PReMI 2025*, Springer LNCS

We tested how much an LLM's answer changes if you only change who it thinks it's talking to. Built two things for it: The Life of X (swap names/identity markers, see how the story changes) and RECAP (ask for culturally-specific recommendations, grade them by hand and automatically). Ran it on GPT-4, Gemini and Claude. All three default to Western norms unless you tell them not to.

## Some things I've built

**[otel-pattern-sampler](https://github.com/sakshitposting-irl/otel-pattern-sampler)** — OTel Java agent extension, drops a noisy root span by name before it hits the exporter. Had one span pattern flooding a trace backend at work and neither "turn down sampling globally" nor "go edit the app" was a good fix, so this.

**[summarize-for-noobs](https://github.com/sakshitposting-irl/summarize-for-noobs)** — Streamlit app, summarizes text.

**[Othello-AI](https://github.com/sakshitposting-irl/Othello-AI)** — Reversi agents.

**[torch-mnist](https://github.com/sakshitposting-irl/torch-mnist)** / **[fmnist-torch-cnn](https://github.com/sakshitposting-irl/fmnist-torch-cnn)** — old PyTorch stuff from when I was learning it. Not deleting these.

Also a [Java text editor](https://github.com/sakshitposting-irl/Java-text-editor) and a bunch of other repos I'm not going to list individually.

## Writing

Medium, mostly "how does this actually work":

- Process Isolation: Linux Namespaces & cgroups
- What Happens When: Linux boots from power to systemd
- What Happens When: You Hit A URL
- Context Switch: The Illusion of Continuity

Older stuff is ML — transformers, GANs, word embeddings, some RL.
