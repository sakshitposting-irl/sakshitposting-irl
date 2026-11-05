# Hi, I'm Saksham

Platform / DevOps engineer. I run production Kubernetes for a multitenant SaaS: 7 clusters, ~100 nodes, ~160 services. Outside the day job I follow whatever's annoying me, which has been ML, then Linux internals, and lately tracing and Kubernetes networking.

📫 saksh.am@outlook.in · ✍️ [medium.com/@saksh-am](https://medium.com/@saksh-am) · 💼 [LinkedIn](https://linkedin.com/in/saksh4) · 𝕏 [x.com/xoredump](https://x.com/xoredump)

find more of me: [saksh.fyi](https://saksh.fyi) · the work version: [dev.saksh.fyi](https://dev.saksh.fyi) · blog: [blogs.saksh.fyi](https://blogs.saksh.fyi)

## Day job, briefly

- Infrastructure/Security/DevOps @ Enveu|Axis360.
- Moved 50+ services from AMD64 to ARM64 with zero downtime, cutting compute cost 25-30% at the same scale.
- Automated ACME TLS behind an L4 load balancer on bare-metal clusters, and fixed hairpin traffic losing the PROXY protocol header with CoreDNS rewrites.
- Made hour-long async jobs survive spot interruptions, scale-downs and deploys by handling SIGTERM properly.
- Stack: EKS + Karpenter, Terraform, Jenkins, Envoy Gateway, OpenTelemetry, Elastic.

## Things I fixed upstream

**[fluent-bit](https://github.com/fluent/fluent-bit/commit/d17e94305df9847599f474dc4c31318a026581b7)**: the official install script silently broke on every Debian/Ubuntu box after packages.fluentbit.io started 302-ing to S3; `curl` fetched an empty GPG key and `gpg` gave up. One flag. Merged.

**[opentelemetry-helm-charts #2377](https://github.com/open-telemetry/opentelemetry-helm-charts/pull/2377)**: the kube-stack chart's values schema rejected `instrumentation.java.extensions` even though the Operator CRD supports it, so you couldn't load a Java agent extension through Helm at all. Found this trying to deploy the sampler below. Merged.

## Some things I've built

**[cyclops](https://github.com/sakshitposting-irl/cyclops)**: Kubernetes controller (Go, kubebuilder) that watches cert-manager Certificates and emails you or posts to Slack when one is expired, never issued, or overdue for renewal. A healthy cluster sends nothing. Built mostly because I wanted to write a controller; it needs no Prometheus stack, and the report carries cert-manager's own failure details. Beta, and it ships releases.

**[otel-pattern-sampler](https://github.com/sakshitposting-irl/otel-pattern-sampler)**: OTel Java agent extension that drops a noisy root span by name (and its whole child tree) before it hits the exporter. One span pattern was flooding our trace backend at ~60 GB every 6 hours, and neither "turn down sampling globally" nor "go edit the app" was a good fix. Growth is now ~60 GB every 4-5 days, about 95% less.

## Papers

**[Investigating Cultural Bias: A Comparative Study of Large Language Models](https://doi.org/10.1007/978-3-032-18477-1_45)**
with Pooja Singh, Sonia Khetarpaul and Unnat Sharma. *PReMI 2025*, Springer LNCS.

We tested how much an LLM's answer changes if you only change who it thinks it's talking to. Built two things for it: The Life of X (swap names/identity markers, see how the story changes) and RECAP (ask for culturally-specific recommendations, grade them by hand and automatically). Ran it on GPT-4, Gemini and Claude. All three default to Western norms unless you tell them not to.

Also fourth author on **[Benchmarking LLM-powered Chatbots](https://arxiv.org/abs/2308.04624)** (arXiv, 2023), from before any of this was my job.

## Writing

On [blogs.saksh.fyi](https://blogs.saksh.fyi), RFC-style memos about things that broke:

- [They Did Surgery on a Process](https://blogs.saksh.fyi/gdb-live-process-surgery/): fixing a stuck deploy by changing an environment variable in a running process with gdb
- [Logs in Translation](https://blogs.saksh.fyi/logs-in-translation/): how a log travels from app to store
- [Observability, My Dear Watson](https://blogs.saksh.fyi/observability-my-dear-watson/): what observability actually means
- [Outbox Your Indexes, Index Your Outbox](https://blogs.saksh.fyi/index-your-outbox/): why a polling transactional outbox slowly eats a CPU core, and the partial index that fixes it
- [4, No Reason](https://blogs.saksh.fyi/4-no-reason/): eight eMudhra intermediate CA keys turned out to be guessable, and how fast browsers moved to block them
- [The Art of the Shard](https://blogs.saksh.fyi/tune-your-es/): Elasticsearch from index to shard to data stream lifecycle, using the numbers from the day a node filled up with traces that were never deleted

Coming next, RFC 0007 to 0009: metrics, traces, OpenTelemetry.

And on Medium, mostly "how does this actually work":

- Process Isolation: Linux Namespaces & cgroups
- What Happens When: Linux boots from power to systemd
- What Happens When: You Hit A URL
- Context Switch: The Illusion of Continuity

Older stuff is ML: transformers, GANs, word embeddings, some RL.

## Old stuff, kept on purpose

[summarize-for-noobs](https://github.com/sakshitposting-irl/summarize-for-noobs) (Streamlit summarizer), [Othello-AI](https://github.com/sakshitposting-irl/Othello-AI) (Reversi agents), [torch-mnist](https://github.com/sakshitposting-irl/torch-mnist) and [fmnist-torch-cnn](https://github.com/sakshitposting-irl/fmnist-torch-cnn) (from when I was learning PyTorch), a [Java text editor](https://github.com/sakshitposting-irl/Java-text-editor), and a bunch of other repos I'm not going to list individually.

---

If you've hit any of these problems and want to compare notes, email's above.
