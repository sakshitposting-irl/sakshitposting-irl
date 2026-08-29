# Hi, I'm Saksham

Most of what I do lately is Java, Python and Linux, pointed at tracing and OS internals. I like the layer where you find out that the thing you assumed was one step is actually eleven.

I also came up through ML, and I still have a foot in it — my paper on cultural bias in LLMs came out at PReMI 2025. So the two halves of this profile look a bit unrelated, and honestly they kind of are. I just find both interesting.

📫 sakshamsrivastava0000@gmail.com · ✍️ [medium.com/@saksh-am](https://medium.com/@saksh-am) · 💼 [LinkedIn](https://linkedin.com/in/s-aksh)

## What I'm working on

### [otel-pattern-sampler](https://github.com/sakshitposting-irl/otel-pattern-sampler)

An OpenTelemetry Java agent extension that drops a noisy root span by name — a poller, a health check, an outbox job — before it ever gets recorded or exported. No changes to the app being instrumented.

I built it because one span pattern was flooding a trace backend, and the options were all bad: turn down sampling everywhere and lose the traces you actually want, or go edit the app. This is the third option.

```
-Dotel.javaagent.extensions=/path/to/otel-pattern-sampler.jar
otel.pattern-sampler.drop-root-span-pattern=^YourNoisySpanName$
```

Under the hood it registers an `AutoConfigurationCustomizerProvider` through `ServiceLoader` and wraps the SDK sampler in a `parentBased` decorator. Root `INTERNAL` spans matching the regex get dropped along with their children; everything else samples exactly as before. Leave the pattern unset and it does nothing at all.

## Paper

**[Investigating Cultural Bias: A Comparative Study of Large Language Models](https://doi.org/10.1007/978-3-032-18477-1_45)**
with Pooja Singh, Sonia Khetarpaul and Unnat Sharma — *PReMI 2025*, Springer LNCS

We wanted to know how much a model's output shifts when you only change who it thinks it's talking about. So we built two tests: **The Life of X**, which swaps identity markers like names and watches the story change, and **RECAP**, which asks for culturally-specific recommendations and grades the answers by hand and by machine. GPT-4, Gemini and Claude all drift the same way — they default to Western norms unless you explicitly tell them not to.

## Writing

I have an ongoing thing on Medium where I take something I use every day and follow it all the way down:

- *Process Isolation: Linux Namespaces & cgroups*
- *What Happens When: Linux boots from power to systemd*
- *What Happens When: You Hit A URL*
- *Context Switch: The Illusion of Continuity*

Older posts are the ML ones — transformers, GANs, word embeddings, a bit of RL.

## Also on here

A few older things I still like: [Othello-AI](https://github.com/sakshitposting-irl/Othello-AI) (agents playing Reversi), [summarize-for-noobs](https://github.com/sakshitposting-irl/summarize-for-noobs) (a Streamlit summarizer), and some PyTorch notebooks from when I was learning it — [torch-mnist](https://github.com/sakshitposting-irl/torch-mnist), [fmnist-torch-cnn](https://github.com/sakshitposting-irl/fmnist-torch-cnn).

Currently reading more of the OpenTelemetry Java agent source than is strictly reasonable.
