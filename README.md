# Study Quest 📚

A single-file study app that teaches you **any university subject** with theory + practice, like a personal teacher.

Built by Malak Abdelkhalek. Evolved from [PCAP-prep](https://github.com/malakabdelkhalek/PCAP-prep).

## Subjects
| Subject | Status |
|---------|--------|
| 🐍 PCAP — Python | ✅ Full content |
| 🦄 Django | 🚧 Content coming (Stage 2) |

## Features
- **Welcome screen** — greets you by name, shows streak + XP, one card per subject with progress % and days to exam
- **+ Add subject** — name, exam date, type (python / django / sql / theory)
- **Per-subject sections** — Today plan, Teacher mode, Learn, Practice, Mock exam, Weak spots
- **Shared streak + XP** across all subjects
- **Practice lab** — Python runs in the browser (Brython)
- Themes: White / Dark / Night / Auto · Phone-first layout · Sound effects

## Content format
Each subject lives in `app/content/<id>.json`:
```json
{
  "meta": { "id": "...", "name": "...", "icon": "...", "type": "python|django|sql|theory" },
  "examWeights": { "chapter-id": 0.34 },
  "mockCount": 40,
  "chapters": [...],
  "cards": [...],
  "mcq": [...],
  "topics": { "topic.slug": "Human name" },
  "boards": [...]
}
```

## Run locally
```bash
cd app && python3 -m http.server 8000
# open http://localhost:8000
```

## Build PCAP content
```bash
pip install weasyprint
cd build
python3 export.py       # → app/notebooks.json
python3 mcq.py          # → app/mcq.json
python3 explain.py      # → app/explain.json
python3 boards.py       # → app/boards.json
python3 make_content.py # → app/content.json  (then copy to app/content/pcap.json)
```
