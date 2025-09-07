# AI Use Log

Quick notes on where I used AI while finishing **Beginning Bioinformatics (Part 3)**. I wrote and ran all final code myself and double-checked outputs with small tests/sample data.

## Entry 1 — GitHub + Colab wiring

**Tool/model & version:** ChatGPT (GPT-5)
**What I asked for:** A simple checklist to create the repo, add `docs/` and `notebooks/`, save my Colab notebook to `notebooks/Bioinformatics_Module03.ipynb`, and make a `week3-submission` tag.
**Snippet of prompt(s):** “I’m new to Git + Colab—give me step-by-step with exact paths and the tag link I should submit.”
**What I changed before committing:** Wrote my own `README.md` line (Name + UTA ID + section), edited commit messages so they describe the change, and kept the repo public.
**How I verified correctness (tests, sample data):** Confirmed the notebook shows up under `/notebooks/` in GitHub, that `docs/ai_usage.md` renders, and that the tag URL looks like `/tree/week3-submission`.

## Entry 2 — P6–P8 (input, lists, slicing)

**Tool/model & version:** ChatGPT (GPT-5)
**What I asked for:** Short, runnable examples for `input()`, list replace/append/insert, and basic string/list slicing.
**Snippet of prompt(s):** “Give me minimal snippets for P6–P8 that I can paste into Colab.”
**What I changed before committing:** Renamed a few variables to be clearer, added comments on 0-based indexing and non-inclusive slice ends, and printed small examples so outputs are obvious.
**How I verified correctness (tests, sample data):** Ran each cell and checked the exact printed result (e.g., `my_list[2:4]` → `["World", "Alfred R. Wallace"]`).


## Entry 3 — Rosalind #7 (DNA → RNA)

**Tool/model & version:** ChatGPT (GPT-5) + Biopython (`Bio.Seq.Seq`)
**What I asked for:** A robust Colab cell that reads a single-line DNA file and safely transcribes **T→U** (handling extra text/blank lines).
**Snippet of prompt(s):** “My dataset has stray text. Help me filter to A/C/G/T and then do DNA→RNA cleanly.”
**What I changed before committing:** Simplified the cleaning step (`"".join(ch for ch in raw.upper() if ch in "ACGT")`), and I kept a plain-Python fallback (`dna.replace("T","U")`) next to the Biopython version.
**How I verified correctness (tests, sample data):** Checked that `len(dna) == len(rna)`, spot-checked the first/last 50 characters, and made sure the printed RNA is one continuous line with no spaces.


## Entry 4 — P13–P15 (file I/O + looping)

**Tool/model & version:** ChatGPT (GPT-5)
**What I asked for:** Idiomatic patterns for `read()`, `readline()`, `readlines()`, using `join()`, and printing lines without accidental blank lines.
**Snippet of prompt(s):** “Show me clean file-reading examples and how to avoid the extra newline in a loop.”
**What I changed before committing:** Switched to `print(line.rstrip())` in loops, used `enumerate(..., start=1)` for even-numbered lines, and added comments explaining why.
**How I verified correctness (tests, sample data):** Used a tiny `practice.txt` and confirmed outputs match exactly (even lines only, no extra blank lines).


## Entry 5 — Dictionaries + word count (Rosalind #5)

**Tool/model & version:** ChatGPT (GPT-5)
**What I asked for:** A concise `Counter` solution plus a pure-dict approach (including a “count on first-seen only” variant).
**Snippet of prompt(s):** “Give me a short word-count solution and one using `.count()` only for unseen tokens.”
**What I changed before committing:** Kept the `Counter` version for clarity and printed results in a sorted order so runs are stable.
**How I verified correctness (tests, sample data):** Compared against a tiny handmade line: `red red blue red` → `red:3, blue:1`.



## Entry 6 — FASTA + GC% (Rosalind #9)

**Tool/model & version:** ChatGPT (GPT-5) + Biopython (`SeqIO.parse`, `SeqUtils.gc_fraction`)
**What I asked for:** Minimal example to parse FASTA, print each ID’s GC%, and report the record with the highest GC.
**Snippet of prompt(s):** “Small script to parse FASTA, compute GC%, and track the max GC record—keep it readable.”
**What I changed before committing:** Rounded to 6 decimals to match common Rosalind outputs and added a quick check for empty sequences.
**How I verified correctness (tests, sample data):** Ran on the sample FASTA, spot-checked one sequence by hand, and confirmed the reported max ID matches the manual check.


### Closing note

I used AI mainly for quick scaffolding and reminders. I rewrote/cleaned the final code to fit the assignment and verified everything with small tests or sample data before committing.
