# Kevin Beltrán

Systems & Industrial Engineering student. I build production systems: an ERP that a paint factory runs its accounting on, and a multi-sport betting engine that only ships a pick when it can prove an edge against the closing line.

Most of what I enjoy sits where data meets a real decision — pricing, inventory, forecasting, risk.

---

## Projects

### [Pantón Color](https://github.com/Kevinbeltran123/Panton_Color) — ERP in production

A web/PWA ERP that replaced the paper notebooks of [Pantón Color](https://pantoncolor.com), a Colombian paint factory. Ten modules covering accounting, color formulas, raw-material inventory, quotations, and production costing.

The parts worth looking at:

- **Colombian tax retentions** (ReteFuente / ReteIVA / ReteICA), monthly periods with locked closings, and an append-only audit log.
- **Money-safe by construction** — business logic lives in Postgres `SECURITY DEFINER` RPCs behind Row-Level Security, so amounts are computed server-side and cannot be tampered with from the client.
- **Atomic production runs** — starting a run freezes an ingredient snapshot and deducts inventory in a single transaction.
- Weighted-average costing on material purchases.

`Next.js 16` · `React 19` · `TypeScript` · `Supabase / PostgreSQL` · `RLS` · `Tailwind` · 248 tests

---

### [Betting Intelligence Platform](https://github.com/Kevinbeltran123/Betting-Platform) — quantitative edge detection

Detects statistical edge with a gradient-boosting ensemble, has an LLM validate the pick, and delivers it over Telegram. A human places the bet; nothing is automated end to end.

**The core thesis is a discipline, not a feature:** ship a pick only when CLV beats the Pinnacle closing line by more than +3%. If there is no edge, the system sends nothing. Measuring against the closing line is the honest way to tell signal from variance.

- Ensemble of XGBoost / CatBoost / LightGBM, with Dixon-Coles and bivariate Poisson goal models.
- Sport-agnostic core with a plugin layer per sport.
- Every secret loads from the environment through Pydantic settings — no credentials in code.

`Python 3.12` · `Polars` · `XGBoost / CatBoost / LightGBM` · `Pydantic v2` · `Supabase` · `uv` · 874 tests in CI

---

### [UnibaBot PDA](https://github.com/Kevinbeltran123/Unibabot_PDA) — LLM agent for compliance

Given an Academic Development Plan as a PDF, the agent checks it against 179 institutional guidelines and returns a report with cited evidence and prescriptive corrections. Includes a head-to-head benchmark of a rule-driven dispatcher against semantic RAG.

`Python` · `FastAPI` · `Qwen 2.5 14B` · `Docling` · `RAG` · `Next.js` · IEEE technical report

---

### [Macroly](https://github.com/Kevinbeltran123/UI-UX-Macroly) — PWA, live

Spanish-language grocery PWA with real-time macronutrient tracking, built around WCAG accessibility and UX research.

**Live:** [macroly.vercel.app](https://macroly.vercel.app)

`Next.js 16` · `TypeScript` · `Zustand` · `Supabase` · `PWA` · `WCAG`

---

## Contact

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kevin-beltran-320859222)
