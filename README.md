# Lawrence King

**Founder of Visual Story Factory · Local AI systems, workflow automation, and videography**

Before AI, I made hip-hop, organized local concerts, and worked with video. That’s where I learned to listen for a bad mix and notice when a cut breaks a scene. Those instincts still drive my engineering. A render can finish successfully and still deliver a shot I would never show an audience.

I learned by building the pieces I needed. My public trail runs from a data science notebook in 2025 to a two-machine Linux setup, a local AI media review desk, and a mixed-GPU filmmaking workflow. Here are the milestones I can put a date and a result to.

### June 2025 · Data science in Jupyter

One of my earliest public artifacts is [DataScienceEcosystem](https://github.com/Lawrenceckingjr/DataScienceEcosystem), a Jupyter notebook from my data science studies. I keep it here because it shows the starting point for the work below.

### October 2025 · Getting two machines to work together

My first attempt to connect my Nebula and Forge machines over SSH returned “No route to host.” I got the direct Ethernet link working, verified remote access, and mounted an NFS share so one machine could use files on the other. I also traced a separate Linux Wi-Fi problem: the system detected the USB wireless adapter, but the networking tools had no usable interface. Learning to separate a routing failure from a driver problem mattered later when my AI jobs began spanning devices.

### February 2026 · Organizing AI research on Windows

On Windows 11 Pro, I set up **LumaRoleRAG**, a research workspace for studying image and video models. I organized source PDFs, processed text, an index, and query logs so I could trace an answer back to the material I was studying. This was an early step from using AI to answer questions toward designing how a tool should support an investigation.

### October 2026 · Building a local AI review desk

With **Shumai**, I brought media uploads, viewing, comments, and local model chat into one review desk. Getting a model to respond quickly was only half the job. An image-caption check scored **0/20** even though inference was running. I investigated the failure and got a diagnostic run to **20/20** on that check. That experience changed what I measure: latency tells me how long an answer took; a task-specific check tells me whether the answer helped.

### October–November 2026 · Putting a desktop GPU to work on a laptop

I connected a **24 GB Radeon RX 7900 XTX** to an HP Victus laptop through an **M.2-to-OCuLink eGPU link** with its own desktop power supply. The laptop also carries an **8 GB RTX 4060**. On Ubuntu 24.04 LTS, I validated local inference through Vulkan and ROCm/HIP, checked the hardware under load, and ran a 27B-class language model locally. I earned the **AMD ROCm Certified Associate** credential in November.

### November 2026 · From automation to filmmaking

**Workflow automation.** I connected n8n to ComfyUI with a JSON request, captured the returned job ID, and checked that the image was actually saved. That last check is the one I care about: a service accepting a request and a user receiving a deliverable are two different events.

**Dragon Forge.** In one local run, my mixed-GPU workflow assembled three 10-second shots into a 30-second sequence at 60 fps in under 16 minutes. A later pilot demonstrated restart recovery: after the dispatcher stopped, it recognized the completed first shot and continued with the next two. I could also trim the assembled sequence without paying the compute cost of generating it again.

**What I’m working on now.** A technically valid video can still lose a character’s likeness between cuts. I’m testing how to preserve faces and wardrobe across shots, and how to distinguish intentional quiet from unusably low audio. I review both the decoded media and the scene itself before I call a take good.

[Connect with me on LinkedIn](https://www.linkedin.com/in/lawrence-king-22691459/)
