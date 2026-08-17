# InjectLab, a Prompt-Injection Training Range

A single-file, offline sandbox for practising prompt injection against **simulated**
defence layers that tell you *why* they blocked you.

Open `index.html` in any browser. No build step, no install, no network calls.

## Why it exists

Most prompt-injection material shows you payloads to copy. Copying a payload teaches you
nothing once the defence changes, and the good defences change constantly. InjectLab is
built the other way round: it refuses to hand over a working phrase, and instead makes the
defence explain its own reasoning so you learn to diagnose.

## What is inside

Three levels, mirroring the objectives that real attacker-facing challenges use:

| Level | Objective |
| --- | --- |
| Spill the Toolbox | Recover the names of the tools the assistant can call |
| Ghost Tools | Establish which tools exist but are hidden from you |
| Skeleton Key | Get a value out of the system that the output filter is watching for |

Three simulated defence layers sit between you and the objective, and each one **labels
what it caught**:

- **INPUT**, a filter on your prompt before the model ever sees it
- **MODEL**, the refusal behaviour of the assistant itself
- **OUTPUT**, a filter on the response that catches secret-shaped values

Two difficulties. **Normal** is forgiving and a single technique can win, which is enough
to learn what each layer does. **Hard** is intent-aware: it uses a broad input blocklist,
refuses answers that fall out of the task as a by-product, and requires you to combine at
least three technique signals before anything gets through.

## Important, read this

This is a **rule-based simulator, not a live language model.** It approximates how layered
defences behave so you can practise diagnosis safely and offline. Beating InjectLab does
not mean you can beat a production system, and it is not intended to produce payloads for
one.

Use it on systems you own or are authorised to test. The point is understanding how these
defences fail, which is the same understanding you need in order to build them properly.

## Tech

Vanilla HTML, CSS and JavaScript in one file. No frameworks, no dependencies, no network
requests, nothing leaves your device.

## License

[MIT](LICENSE)
