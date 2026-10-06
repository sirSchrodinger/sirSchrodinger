Physics undergrad at Bilkent. I build computer vision and backend systems that
have to keep running when nobody is watching them.

Most of my work ends up being about measurement: checking whether the number I
just reported is actually true. Two of the repositories below exist in their
current form because the first evaluation was wrong and it took a long time to
notice.

### Current work (the code is private)

**Greenhouse person detector.** A D-FINE-M student trained in-house watches my
family's greenhouse cameras over a 4G line. On 2,918 frames I labelled it finds
94% of people where stock YOLO11s finds 50%, at the same false-alarm rate.

**Player detection from scratch.** A football player detector written in NumPy and
CuPy with hand-derived gradients and no machine-learning library.

The write-ups, with their limits, are at [cv.sirschrodinger.com](https://cv.sirschrodinger.com).

### [greenhouse-person-detection](https://github.com/sirSchrodinger/greenhouse-person-detection)

An earlier version of the greenhouse detector (YOLO11s plus a DINOv2
verifier). The model running now is a D-FINE-M student that is not in this
repo. The part worth reading is the audit: the original validation split
shared scenes with training (48% of validation frames also appeared in train,
42 of them pixel-identical), so the reported accuracy was inflated. The split
is scene-aware now, and six copies of the same forward pass were merged into
one with the numerical drift measured rather than assumed.

### [llm-agent-runtime](https://github.com/sirSchrodinger/llm-agent-runtime)

An autonomous agent daemon. Goals decompose into work packets, each packet
routes through a panel of eight backends from five providers, and the executor
can actually change files on the machine. Most of the code is about limiting
what it can do: shell commands run in a bubblewrap sandbox, and write tools
are refused unless the call is marked as a write.

### [papers-net-core](https://github.com/sirSchrodinger/papers-net-core)

Research orchestration across five LLM families: fan a question out, make them
argue, then try hard to prove the surviving answer wrong. Most of the code is
there to refuse text that has not survived a check: citation resolution,
chain-of-verification, Lean checking, dimensional analysis, conformal
calibration.

### [old-kernel-modern-android](https://github.com/sirSchrodinger/old-kernel-modern-android)

What breaks when you put Android 10 on a Linux 3.4 kernel with 2013-era vendor blobs, and how each of the ten
root causes was found: by measurement, not guesswork.

---

Also: the analysis for a collaborator's CT radiomics study on bone lesions
(the question and the data are theirs; AUC 0.985 with patient-grouped
cross-validation, single centre), and a few Cloudflare Workers sites that run
themselves.

[cv.sirschrodinger.com](https://cv.sirschrodinger.com)
