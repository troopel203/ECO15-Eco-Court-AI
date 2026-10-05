# ECO-15 Pro
1. Open this folder in VS Code (File > Open Folder).
2. Double-click index.html (or right-click > Open with Live Server / Open in Browser). Use Chrome or Edge.
3. Click "Load 3 demo cases" on the Dashboard. Add a Gemini key in Settings for AI answers (optional).
Needs internet (PDF.js, fonts, Gemini). AI research aid only. Not legal advice.

## v3 notes
- Gemini 503 = Google servers busy (not your key). The app retries 3x, switches to backup models, then falls back to a local extractive answer.
- "AI-verify" tick box runs a second Gemini pass that marks each claim supported / partial / unsupported.
- Questions like "list all laws / provisions" are answered by the verbatim regex extractor (no AI, nothing invented).
- Eval page now compares BM25 vs on-device LSA model vs hybrid.

## v4: real pre-trained models (run in the browser)
Serve with VS Code "Live Server" (right-click index.html > Open with Live Server) so models are cached. First use downloads ~250 MB.
- Embeddings: Xenova/all-MiniLM-L6-v2 | Reranker: Xenova/ms-marco-MiniLM-L-6-v2 (MS MARCO)
- Answers (no key): Xenova/distilbert-base-cased-distilled-squad (SQuAD) | Verifier: Xenova/nli-deberta-v3-xsmall (NLI)
- OCR: Tesseract.js for scanned pages. New page: "Verify a claim". Eval page: "Test claim verifier".
