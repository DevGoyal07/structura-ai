# Structura.AI

**Compressing structural design validation from days to seconds.**

![Structura.AI dashboard](assets/dashboard.png)

Structura.AI is a web-based AI pre-screening tool that gives civil and structural engineers a fast safety check during the drafting phase — *before* committing to a full Finite Element Analysis (FEA) run.

An engineer uploads a 2D structural layout (DXF or node-beam JSON) and basic load parameters. Within ~3 seconds, a trained Convolutional Neural Network returns a color-coded heat map of predicted stress zones — so designs reach formal FEA already refined.

> **Not a replacement for FEA.** Regulatory sign-off still requires a full simulation. Structura.AI shifts the expensive back-and-forth from late-stage simulation rework to fast, low-cost AI feedback in early design — making the formal FEA run a *confirmation* rather than a *discovery*.

🔗 **Live demo:** https://structura-ai-six.vercel.app/
🔗 **Video demo:** https://drive.google.com/file/d/1BTcLa_Psc_5p9EaHb09urKvtiGhzOBNb/view?usp=sharing

---

## The Problem

Traditional FEA (ANSYS, ABAQUS) is slow — 16 to 48 hours for a moderately complex structure — and is almost always run *after* a design is substantially complete. When it flags a failure, the team has to revise the CAD model, rebuild the mesh, and re-run the solver. One full iteration loop can cost close to a working week of senior-engineer time.

## How It Works

| Stage | What Happens |
| --- | --- |
| **Input** | Engineer uploads a 2D layout (`.DXF` or node-beam `JSON`) and enters load parameters |
| **CNN Inference** | A PyTorch CNN maps geometry + loads directly to a predicted stress field — no physics solver |
| **Heat Map** | A color-coded 2D overlay renders on the structural diagram |
| **Insight** | Engineer adjusts the design and re-checks, all before formal FEA |

### Heat Map Color Key

| Color | Stress Level | Interpretation |
| --- | --- | --- |
| 🔴 Red | Above 80% of yield strength | High failure risk — design change required |
| 🟡 Yellow | 50%–80% of yield strength | Caution zone — review recommended |
| 🟢 Green | Below 50% of yield strength | Structurally safe under current load |

## Tech Stack

- **Deep Learning:** PyTorch CNN trained on pre-computed FEA simulation results
- **Backend:** Flask / FastAPI
- **Frontend:** HTML / JS (live site deployed on Vercel)
- **Inputs:** DXF (CAD standard) and structured node-beam JSON
- **Loads:** Point loads, distributed loads (kN, kN/m)

## Performance Targets

| Metric | Target |
| --- | --- |
| Inference latency | < 3 seconds per analysis |
| Prediction accuracy | ≥ 85% agreement with FEA-derived stress maps |
| Supported geometry (Phase 1) | 2D beams, Pratt trusses, Warren trusses |
| Training dataset | 10,000+ pre-run FEA simulations (target) |

## Project Status

Currently at the **technical prototyping** stage:
- ✅ ML pipeline architecture fully mapped
- ✅ Baseline PyTorch CNN implemented
- 🔄 FEA dataset curation underway
- 🔄 Model training & ≥85% accuracy validation
- ⬜ Web MVP (upload + heat map) and pilot launch

## Getting Started

> Adjust the commands below to match your actual project structure.

```bash
# Clone
git clone https://github.com/YOUR_USERNAME/structura-ai.git
cd structura-ai

# Set up a Python environment
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# Run the backend (example — adjust to your entry point)
python app.py
```

## Team — Group CE24B0

| Name | Roll Number |
| --- | --- |
| Abhay P M | CE24B034 |
| Abhishek Rai | CE24B035 |
| Devansh Goel | CE24B056 |
| Dipayan Das Gupta | CE24B059 |
| Lokesh K | CE24B082 |
| Param Shah | CE24B097 |

Built as part of **MS 4810**, 2026.

## License

Released under the [MIT License](LICENSE).
