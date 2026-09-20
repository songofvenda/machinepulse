# MachinePulse

**Retrofit predictive maintenance and a decision twin for Indian MSME manufacturing.**

A ₹3,000 clip-on sensor pod retrofits condition monitoring onto any machine, of any age, in about ten minutes — no rewiring, no PLC, no downtime.

🔗 **Live demo:** _add your Netlify URL here after deploying_

---

## The problem

A typical MSME unit runs 20–100 machines, most of them 10–30 years old, with no data port and no network. Failures are discovered when production stops, around 70% of maintenance is purely reactive, and true utilisation and per-machine energy use are simply unknown.

Industry 4.0 platforms solved this for factories with modern controls and crore-scale budgets. India's MSMEs — the bulk of Indian manufacturing — were quoted a price they could never pay.

## What this demo shows

The page is the product, running on simulated shop-floor data:

- **Live fleet dashboard** — six machines streaming vibration, temperature, current, machine state, utilisation and a health score
- **Fault injection** — induce a bearing fault on VMC-04 and watch the health score collapse in real time
- **WhatsApp alert** — the alert the maintenance person actually receives, with the fault, health score, ticket ID and the spare flagged for reorder
- **NFC machine record** — tap any machine's tag to open its full record: running hours, service history, open tickets, report a problem
- **Digital twin** — move the sliders and project 180 days forward with a P10–P90 confidence band, holding every other variable constant

## How it works

| Stage | What happens |
|-------|--------------|
| Connect | Vibration, temperature, current and sound read from outside the machine. A split-core clamp reads the supply line without touching a conductor. |
| Analyse | Each machine learns its own normal. The current signature alone separates off from idle from running under load — true OEE with no PLC. |
| Predict | Named faults with a failure window given as a probability band, not a single date. |
| Act | Andon light, WhatsApp alert in the technician's language, ticket raised, spare flagged before it is needed. |

## Hardware

ESP32 · 3-axis accelerometer · non-contact IR temperature sensor · split-core current clamp · MEMS microphone, in a 3D-printed PETG enclosure with a magnetic mount. Edge gateway buffers locally so the system keeps working when the internet does not.

## Running locally

No build step, no dependencies. Clone and open `index.html` in a browser.

```bash
git clone https://github.com/<your-username>/machinepulse.git
cd machinepulse
open index.html
```

## Status

Working prototype. The sensing hardware, alerting and twin logic run on an instrumented test rig; the data in this web demo is simulated so the product can be explored without a live plant. MachinePulse monitors machine health only — it never controls a machine.

Built by **Smartronics Technology**, Pune.
