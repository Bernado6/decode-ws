# Designing End-to-End AI Systems

**Safaricom Decode · Chalk Talk 1 · 08:00 – 10:00**

A two-hour, hands-on session that takes a room from `y = mx + c` to a production AI architecture they can draw on paper. The room builds the answer first; the slide confirms it. Expect votes, arguments, prizes and a design studio.

Everything lives in one file: [`deck.html`](deck.html). Open it in a browser. No build step, no server, no internet needed except for the optional external demos listed below.

## What participants leave with

1. **An architecture** — Data → Model → API → Frontend, drawn by hand for a real Safaricom-style problem.
2. **A pattern vocabulary** — RAG, model cascade, fallback chain, agent, human-in-the-loop, batch vs. real-time.
3. **Rules for real actions** — auth, idempotency, retries, approval gates and audit logs for anything that touches money, devices or partner APIs.

Not covered: data-pipeline internals and security threat models. Those have their own sessions.

## Running the deck

Open `deck.html` in Chrome or Edge, press **F** for fullscreen, and press **N** to see the presenter notes for the current slide. Deep-link to a slide with `deck.html#12`.

| Key | Action |
|---|---|
| `→` `↓` `Space` `PgDn` | Next slide / reveal next fragment |
| `←` `↑` `PgUp` | Previous slide |
| `Home` / `End` | First / last slide |
| `N` | Toggle presenter notes |
| `F` | Toggle fullscreen |
| `T` | Start / stop the timer on the current slide |
| `P` | Add an airtime winner (name + amount) to the winners board |
| Click right 85% of the stage | Next · click left 15% | Previous |
| Swipe | Works on touch devices |

Some slides are interactive. Clicking a card does something before the deck advances:

- **Reveal cards** (finger vote, spam filter, pattern scenarios, defences): click to flip and show the answer.
- **Layer Sort**: click a card to cycle Data → Model → API → Frontend, then press **Check answers**.
- **GenAI circle** on the Venn slide: click to slide it into its correct place.
- **Count cards** (role poll, exit ticket): click once per raised hand.
- **Matatu Fare Learner**: an inline gradient-descent demo with sliders, single-step, auto-train, drift and retrain.

## Session run-sheet

| Time | Slides | Segment | Activity | Prize |
|---|---|---|---|---|
| 08:00 | 1–3 | Opening | Hands-up poll: spam filter, M-PESA, recommendations, chatbots | |
| 08:04 | 4 | Where does it sit? | AI ⊃ ML ⊃ DL Venn; argue where GenAI goes | KSh 150 |
| 08:05 | 5 | Deliverables | State the three things they leave with | |
| 08:08 | 6–8 | Fundamentals | `y = mx + c` → guess matatu fares → loss, gradient descent, epoch | KSh 150 |
| 08:15 | 9 | Live demo | Matatu Fare Learner, then TensorFlow Playground | KSh 150 |
| 08:22 | 10 | One line to a brain | Weights, biases, activations, layers; Transformer Explainer | |
| 08:25 | 11–12 | Three types of ML | Finger vote on six scenarios | KSh 150 |
| 08:32 | 13–14 | You are the spam filter | Thumbs vote, Teachable Machine, then an unseen message → drift | KSh 150 × 2 |
| 08:40 | 15 | Training loop | Collect → train → evaluate → deploy → monitor | |
| 08:43 | 16–17 | It works on my laptop | Pairs list what breaks at 1M users; Colab prototype | KSh 150 |
| 08:50 | 18 | The spine | Data → Model → API → Frontend | |
| 08:53 | 19–20 | Layer Sort | Groups sort 16 components into four layers | KSh 200 |
| 09:00 | 21–22 | Inside each layer | Design details; build vs. buy | |
| 09:05 | 23–25 | Patterns | Six patterns; "which pattern fixes this?"; cascade deep-dive; NotebookLM | KSh 150 each |
| 09:15 | 26–29 | Concierge case study | Red-team the concierge; every attack has a named defence; payments pattern | KSh 200 |
| 09:30 | 30 | Checklist | Silent minute: score an app on your phone | |
| 09:45 | 31 | Design Studio | Groups of 4 draw an architecture on A3 for one brief | KSh 200 |
| 09:56 | 32 | Who builds each layer | Roles along the spine; poll which one they want | |
| 09:58 | 33–36 | Close | Exit ticket, three takeaways, winners board, Q&A | |

## External demos (open before the session)

Each is linked from a 🌐 button on the relevant slide. Sign in where needed beforehand so nothing stalls on stage.

| Slide | Tool | Use |
|---|---|---|
| 9 | [TensorFlow Playground](https://playground.tensorflow.org/#activation=tanh&batchSize=10&dataset=gauss&regDataset=reg-gauss&learningRate=0.03&regularizationRate=0&noise=0&networkShape=6,6&seed=0.99828&showTestData=false&discretize=false&percTrainData=50&x=true&y=true&xTimesY=false&xSquared=false&ySquared=false&cosX=false&sinX=false&cosY=false&sinY=false&collectStats=false&problem=regression&initZero=false&hideText=false) | Same training loop, but fitting a surface with 6+6 neurons. Preset is regression on the gauss dataset. 60 seconds. |
| 10 | [Transformer Explainer](https://poloclub.github.io/transformer-explainer/) | Type "Safaricom is the largest" and show the next-token probabilities. 90 seconds. |
| 13 | [Teachable Machine](https://teachablemachine.withgoogle.com/train/image) | Two volunteers train a phone-vs-notebook webcam model, then show it an unseen object. |
| 16 | [Colab notebook](https://colab.research.google.com/drive/14YWeVJA7c0ODALtFtPuyO-jPuLvTRD8a#scrollTo=a4f63ba8) | "The prototype that works on my laptop." 20 seconds, then close it. |
| 24 | [NotebookLM](https://notebook.google.com/notebook/dd631279-5ddf-4476-9515-28dbde3fc074) | RAG with citations, then a question the sources don't cover → the honest "I don't know". |
| 31 | [Excalidraw](https://excalidraw.com/) | Backup whiteboard; redraw the winning architecture cleanly so the room can photograph it. |

## Activities in detail

**Layer Sort (slide 19).** Sixteen components, four layers. Worth arguing about: output guardrails (API, arguably Model) and thumbs-down feedback (Frontend, but it flows back into Data).

**Which pattern fixes this? (slide 24).** Chatbot invents tariffs → RAG. Huge model on trivial questions → model cascade. Provider outage takes the app down → fallback chain. AI refunds up to KSh 50,000 alone → human-in-the-loop. Running late? Do only the first and last.

**Break the Concierge (slide 27).** Groups play a malicious customer, a flaky network, a buggy retry and an offline device. Harvest attacks on the board, then map each to its defence on slide 28:

| Attack | Defence |
|---|---|
| Refund requested twice, or retried by the network | Idempotency keys |
| The model holds the payment credentials | Scoped auth per integration; the model calls your API, your API calls the provider |
| Talked into a KSh 50,000 refund | Approval gates above a threshold |
| Device offline but the app says "done" | Queues and async acks; timeout and retry |
| Provider down and we keep hammering it | Retries, backoff, circuit breakers |
| Nobody knows what the AI actually did | Audit logging: who, what, when, result |

**Design Studio (slide 31).** Groups of four, one brief each, one A3 sheet. Draw the four layers, name the patterns, mark every external call with its defence, and name one thing to monitor. Two groups present for 60 seconds each; judge aloud against the checklist. Photograph every sheet.

Briefs:

1. **Fraud alert** — an M-PESA fraud alert that texts the customer and can freeze a transaction.
2. **Care assistant** — a customer-care assistant that issues airtime refunds and escalates to a human.
3. **Crop doctor** — a farmer photographs a leaf; the app diagnoses and orders inputs through a partner API.
4. **Outage predictor** — predicts network outages, dispatches field engineers, updates the status page.
5. **Room booker** — a campus agent that books rooms through the university calendar API.

## Checklist for any AI design

- **Data** — is data owned by one layer, or does everything query raw sources directly?
- **Model** — did you pick the cheapest build-vs-buy option that meets the bar?
- **API** — could you swap the model vendor without touching the frontend?
- **Frontend** — does the UI handle latency and uncertainty, not just the happy path?
- **Patterns** — which named pattern(s) does this use, and does the whole team know?
- **Integration** — for every external call: auth, idempotency, retries, and an audit log?

## Materials to bring

- Airtime budget: roughly KSh 2,500 across 15 or so prizes (see run-sheet). Press **P** to log winners as you go.
- A3 sheets and markers for the Design Studio, one per group of four.
- Whiteboard space for harvesting answers on slides 16, 27 and 19.
- A laptop signed in to Google (Colab, NotebookLM, Teachable Machine need it) with the webcam enabled.

## Editing the deck

`deck.html` is self-contained: styles, slide definitions, presenter notes and all images (base64) are in the one file. Slides are defined as an array in the script at the bottom, each with a `title`, optional `notes`, optional `tag` (activity label + timer), `links`, `prize`, and an `html` body built from small `row`, `grid`, `card` and `bar` helpers. Edit the file directly and reload.

## Three things to take home

1. **Production-ready is structural**, not a smarter model. Data, Model, API, Frontend as distinct, swappable layers.
2. **The API layer is your leverage.** A clean contract there lets every other layer change independently.
3. **Real actions need real rigour.** Auth, idempotency, retries, approval gates and audit logs are the architecture, not extras.
