# GraphLoom

**Drop in your files. Get an ontology and a knowledge graph — in one HTML page.**

GraphLoom weaves a pile of documents, spreadsheets and images into a typed knowledge graph, and shows you the
ontology behind it. Everything runs in your browser: no install, no server, no account. Open the file, drop a folder,
and explore.

---

## Highlights

- **One file, zero setup** — `ontology-graph-explorer.html` is the whole app.
- **Ontology ⇄ Knowledge graph** — see the classes and relationship types first, then morph into the actual entities.
- **Reads almost anything** — TXT, Markdown, PDF (including scanned), DOCX, HTML, CSV/TSV, XLSX, JSON/JSONL, XML, code,
  logs, and images (JPG, PNG, WebP, GIF, BMP, TIFF) via offline OCR.
- **Understands structure, not just words** — spreadsheet IDs and foreign keys, org charts (including connector lines in
  images), research papers (authors, affiliations, references, citations), key–value records, Mermaid diagrams.
- **Provenance on everything** — each link is marked *explicit*, *inferred* or *co-occurrence*, with the source sentence.
- **Clean identities** — singular/plural, aliases ("UK" = "United Kingdom"), acronyms and spelling variants are merged or
  suggested for one-click review.
- **Readable at any size** — communities, collapsible clusters, hub-first labels, force or hierarchy layout.
- **Optional AI** — an offline in-browser entity model, or NVIDIA NIM (any OpenAI-compatible endpoint) for LLM extraction
  and vision.
- **Exports** — Neo4j Cypher, direct push to Neo4j, Excel workbook (re-importable for review), JSON, CSV triples, Turtle, PNG.
- **Remembers your session** — reopen the page and your last graph is back, exactly as you left it.

## Quick start

1. Download `ontology-graph-explorer.html`.
2. Open it in a modern browser (Chrome, Edge or Firefox).
3. Click **Upload files**, **Choose folder**, or drag files/folders onto the page. Or click **Try sample**.
4. Explore:
   - **Ontology** shows classes (circles) and relationship types (arrows).
   - **Knowledge Graph** shows the entities; double-click a class to explore its instances.
   - Click any node or link for its properties, provenance and source sentences.

> An internet connection is needed the first time, to load the graph and file-reading libraries from public CDNs.
> Your files are never uploaded anywhere.

## How to…

| Task | How |
|---|---|
| Switch views | **Ontology / Knowledge Graph** toggle at the top, or keys **O** / **K** |
| Zoom and move | Scroll or **＋ / −** buttons (**+ / −** keys); drag the background; **Fit** or **0** |
| Change layout | **Layout: force / hierarchy** (bottom right); **Re-layout** reruns the force layout |
| Hide a class | Click it in the legend |
| Reduce clutter | Settings (**[**) → *Readability*: min mentions, max nodes, links shown (explicit / inferred / all) |
| Colour by community | Settings → *Colour by: Community*; *Clusters* collapses communities (double-click a cluster to open it) |
| Fix duplicates | Settings → *Quality* → *Possible duplicates* → **Merge** or **Keep apart** (remembered on re-runs) |
| Search | **/** then type a class or entity name |
| Use the AI entity model | Settings → tick *AI entity model* (one-time ~66 MB download, then offline) → **Re-run extraction** |
| Use NVIDIA NIM / an LLM | Settings → *Extraction engine* → *NVIDIA NIM (LLM)* → endpoint, model and API key |
| Export | **Export** menu → Cypher, Excel, JSON, CSV, Turtle, PNG, or push to Neo4j |
| Review in Excel | Export to Excel, edit the *Review_Status* / class columns, then drop the workbook back in |
| Start over | Settings → Files → **Clear** (also deletes the saved session) |
| Check quality | Settings → *Quality* → **Run self-test** (built-in inputs with known answers) |

Keyboard: **[** settings · **]** details · **O / K** views · **/** search · **+ / − / 0** zoom · **?** help.

## Viewing the graph in Neo4j

Export **Cypher** and run it in Neo4j Browser, or use **Push to Neo4j** with your connection details. Then
`CALL db.schema.visualization()` shows the same ontology.

## Privacy

Parsing, OCR, extraction and the optional AI entity model all run locally in your browser. Data leaves your machine
only if you choose the NIM / LLM engine (sent to the endpoint you configure) or push to your own Neo4j instance. The
saved session lives in your browser's storage only.

## Limitations

- Rule-based extraction is strongest on names, organisations, places, tables and structured documents; for free-form
  prose, the AI entity model or an LLM engine improves recall.
- OCR quality depends on the scan; very noisy pages can produce noise entities.
- Very large corpora (thousands of documents) are better served by a database-backed pipeline.

## License

Add your license of choice (for example MIT) before publishing.
