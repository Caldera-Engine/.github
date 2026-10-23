# Caldera Engine

*A security-first, hardened fork of the Godot Engine designed to protect indie games from asset theft and automated reverse engineering.*

## What is Caldera?

The Caldera Engine is a specialized build of the open-source Godot Engine. It retains 100% of Godot's incredible developer experience, editor tools, and node-based workflow, but completely overhauls the engine's internal runtime architecture and build pipeline to prioritize **application security and anti-tamper resilience.**

## Why We Made It

The indie game industry has a growing problem: **Asset Flipping and Ad-Cloning.**

Standard open-source game engines are built for accessibility, modularity, and ease of use. Unfortunately, this means their cryptographic and resource-loading pipelines are heavily standardized. Malicious actors have built automated, push-button tools (like generic reverse-engineering unpackers) that can strip a compiled game of its assets, scripts, and source code in a matter of seconds. Bad actors use these tools to rip indie games, inject their own advertisements, and re-publish them for profit.

**Caldera was built to break the asset flipper's business model.**

Normal DRM is trash. They throw money at the problem and tell them to make it work however they can which results in things like Denuvo.
We decline this model, and insted turn to *actually using our brains and targeting the tools they use to decompile specificly.* Caldera has practically zero overhead during actual gameplay, and just a ever so slightly (within a margin of error of like... 1%) 35ms startup time cost.

We believe that independent developers deserve to ship their games without the fear that their years of hard work will be stolen and monetized by a script kiddie in five minutes. Absolute, uncrackable DRM is a myth, but **economic deterrence** is very real. Caldera's goal is to raise the "time-to-crack" threshold so high that malicious actors abandon the attempt out of sheer frustration.

## Core Philosophy: Security Through Architecture

Caldera achieves its resilience not by simply adding a password to a zip file, but by fundamentally restructuring how the engine handles data at runtime.

Our approach focuses on **Zero-Choke-Point** design. By removing standard, predictable cryptographic boundaries, we render generic extraction tools and automated memory dumpers completely useless.

### Key Defense Pillars

* **Deep Asset Isolation:** Assets and scripts are no longer protected by a single, monolithic barrier. Caldera utilizes per-file cryptographic binding, meaning the execution state of one asset cannot be reverse-engineered to unlock the rest of the project.

* **Polymorphic Execution:** The engine's internal instruction flow and memory structures shift during the build process, making static analysis and standard disassembly tools blind to the engine's true logic.

* **Automated Memory Hygiene:** Sensitive data and decrypted scripts are aggressively wiped from the system's memory immediately after compilation or execution, preventing dynamic RAM scrapers from grabbing game logic while it runs.

* **Seamless Developer Workflow:** You build your game exactly as you would in standard Godot. Caldera's security features are injected silently and automatically during the SCons compilation and export phases. You focus on the game; Caldera handles the armor.

## Getting Started

Contact us at armyof64@gmail.com to apply for access to Caldera. Caldera is only available to those nearing their shipping date of their product, and will be subject to review before access is granted, given we need to maintain security.

We do not ask for any profit sharing, the use of Caldera is free, but you must ensure the security of the engine build you are given. 

You do not need Caldera to build your game until you plan to release it (Demo, full release, early alpha, etc)! It can import and use default Godot projects so focus on your game until you are close to one of those, then come talk to us!

Let me repeat this: you MUST have a near-complete product to gain access. To protect the engine's obfuscation architecture from falling into the hands of bad actors, we require definitive proof of IP ownership before granting access. Accepted verification methods include:

A live-call screenshare of your backend developer portal (Steamworks, Epic, Apple/Google Play, or itch.io).

A live-call screenshare of your project's source control repository demonstrating long-term commit history (6m-1y+ where any commit can be clicked into a show changes).

Authentication via official studio infrastructure (e.g., emailing from your game's verified web domain or temporarily modifying a live storefront description with a verification code).
## Contributing

Because Caldera relies on proprietary obfuscation and proprietary architectural shifts to maintain its security edge, parts of the cryptographic pipeline are tightly controlled. However, we welcome PRs for upstream Godot merges, performance optimizations, and general engine stability.

*Caldera Engine: Built for creators. Hardened against thieves.*
