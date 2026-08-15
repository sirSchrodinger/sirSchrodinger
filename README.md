Physics undergrad at Bilkent, Ankara. I build computer vision and backend
systems that have to keep running when nobody is watching them.

Most of my work ends up being about measurement — not "does the model work"
but "is the number I just reported actually true". Two of the repositories
below exist in their current form because the first evaluation was wrong and
it took a long time to notice.

### [multicam-football-tracking](https://github.com/sirSchrodinger/multicam-football-tracking)

Player tracking across phone cameras at an amateur football pitch: pitch
calibration, cross-camera identity, IDF1 **0.835** against hand-labelled
ground truth. Almost none of that came from a better model — it came from
fixing what the evaluation was allowed to count.

### [greenhouse-person-detection](https://github.com/sirSchrodinger/greenhouse-person-detection)

Person detection on a greenhouse camera feed, YOLO11s plus a DINOv2
verification pass, running unattended on CPU. The part worth reading is the
audit: the original validation split shared scenes with training — 48% of
validation frames also appeared in train, 42 of them pixel-identical — so the
reported accuracy was inflated. The split is scene-aware now, and six copies
of the same forward pass were merged into one with the numerical drift
measured rather than assumed.

### [llm-agent-runtime](https://github.com/sirSchrodinger/llm-agent-runtime)

An autonomous agent daemon. Goals decompose into work packets, each packet
routes through a panel of eight LLM providers, and the executor can actually
change files on the machine. The interesting problem there is not what it can
do, it is what stops it: three independent brakes, deliberately not one.

### [papers-net-core](https://github.com/sirSchrodinger/papers-net-core)

Research orchestration across five LLM families — fan a question out, make
them argue, then try hard to prove the surviving answer wrong. Most of the
code is not about generating text; it is about refusing to keep text that has
not survived something: citation resolution, chain-of-verification, Lean
checking, dimensional analysis, conformal calibration.

---

Also: radiomics classifier for sclerotic bone lesions (AUC 0.989), and a few
Cloudflare Workers sites that run themselves.

[sirschrodinger.com](https://sirschrodinger.com) ·
[cv.sirschrodinger.com](https://cv.sirschrodinger.com)
