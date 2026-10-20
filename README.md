# Hi, I'm Saksham

No fixed specialty, I just work on whatever's annoying me at the time. That's been ML, then Linux internals, now tracing and Kubernetes networking. 
Day job is running lots of Kubernetes clusters, lots of Docker, some networking, some cybersec and whatever I am allowed to poke at.

Not really a themed portfolio below, just stuff I got into.

📫 sakshamsrivastava0000@gmail.com || saksh.am@outlook.in · ✍️ [medium.com/@saksh-am](https://medium.com/@saksh-am) · 💼 [LinkedIn](https://linkedin.com/in/s-aksh)

find more of me: [https://saksh.fyi](https://saksh.fyi)

## Things I fixed upstream

**[fluent-bit](https://github.com/fluent/fluent-bit/commit/d17e94305df9847599f474dc4c31318a026581b7)** — the official install script silently broke on every Debian/Ubuntu box after packages.fluentbit.io started 302-ing to S3; `curl` fetched an empty GPG key and `gpg` gave up. One flag. Merged.

**[opentelemetry-helm-charts #2377](https://github.com/open-telemetry/opentelemetry-helm-charts/pull/2377)** — the kube-stack chart's values schema rejected `instrumentation.java.extensions` even though the Operator CRD supports it, so you couldn't load a Java agent extension through Helm at all. Found this trying to deploy the sampler below. Merged.

## Some things I've built

**[otel-pattern-sampler](https://github.com/sakshitposting-irl/otel-pattern-sampler)** — OTel Java agent extension, drops a noisy root span by name (and its whole child tree) before it hits the exporter. Had one span pattern flooding a trace backend at work — ~60 GB every 6 hours — and neither "turn down sampling globally" nor "go edit the app" was a good fix, so this. Backend rotates at 10 days and hasn't filled up since.

**[summarize-for-noobs](https://github.com/sakshitposting-irl/summarize-for-noobs)** — Streamlit app, summarizes text.

**[Othello-AI](https://github.com/sakshitposting-irl/Othello-AI)** — Reversi agents.

**[torch-mnist](https://github.com/sakshitposting-irl/torch-mnist)** / **[fmnist-torch-cnn](https://github.com/sakshitposting-irl/fmnist-torch-cnn)** — old PyTorch stuff from when I was learning it. Not deleting these.

Also a [Java text editor](https://github.com/sakshitposting-irl/Java-text-editor) and a bunch of other repos I'm not going to list individually.

## Papers

**[Investigating Cultural Bias: A Comparative Study of Large Language Models](https://doi.org/10.1007/978-3-032-18477-1_45)**
with Pooja Singh, Sonia Khetarpaul and Unnat Sharma — *PReMI 2025*, Springer LNCS

We tested how much an LLM's answer changes if you only change who it thinks it's talking to. Built two things for it: The Life of X (swap names/identity markers, see how the story changes) and RECAP (ask for culturally-specific recommendations, grade them by hand and automatically). Ran it on GPT-4, Gemini and Claude. All three default to Western norms unless you tell them not to.

Also fourth author on **[Benchmarking LLM-powered Chatbots](https://arxiv.org/abs/2308.04624)** (arXiv, 2023), from before any of this was my job.

## Writing

Medium, mostly "how does this actually work":

- Process Isolation: Linux Namespaces & cgroups
- What Happens When: Linux boots from power to systemd
- What Happens When: You Hit A URL
- Context Switch: The Illusion of Continuity

Older stuff is ML — transformers, GANs, word embeddings, some RL.

---

If you've hit any of these problems and want to compare notes, email's above.
