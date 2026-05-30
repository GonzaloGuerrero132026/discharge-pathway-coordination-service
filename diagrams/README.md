# Diagrams

Two Mermaid source diagrams produce the figures used in the report.

| Source | Output | Used as |
|--------|--------|---------|
| `01_architecture.mmd` | `../figures/architecture.png` | Figure 1 (`fig:arch`) |
| `02_sequence.mmd` | `../figures/sequence.png` | Figure 2 (`fig:seq`) |

## How to render

### Quick way: Mermaid Live Editor
1. Open <https://mermaid.live>
2. Paste a `.mmd` file's contents
3. Actions: PNG, save to `../figures/<name>.png`

### Repeatable way: mermaid-cli
```powershell
npm install -g @mermaid-js/mermaid-cli
mmdc -i diagrams/01_architecture.mmd -o figures/architecture.png -w 2100 -H 1500 -b white
mmdc -i diagrams/02_sequence.mmd     -o figures/sequence.png     -w 1700 -H 1300 -b white
```

After rendering, run `pdflatex report.tex` twice from the `report/` directory. The `\IfFileExists` checks in the source pick up the rendered PNGs automatically.
