AI ASSIGNMENT

Python 3.11, Conda research.
Dependencies: torch, transformers 5.16.1, huggingface_hub, pandas, pyarrow,
z3-solver 5.3.1.0, xgrammar 0.2.8, lark, lemminflect 0.2.3, scikit-learn, ipykernel.
Model: Qwen/Qwen3-4B-Instruct-2507 (about 8 GB of weights).
16 GB CUDA memory recommended; GPU is preferred. CPU is also supported.
Logic inputs run on CPU without loading the model. English inputs may need the model.
First run downloads missing model weights and public datasets into data/.

Open reasoning_agent.ipynb and run all cells. No project Python files are needed.
The final Evaluation cell has commented CSV and JSONL lines for private data.
Inputs: context (text or a list of premises), statement, and optional id.
Formulas may use FOLIO's premises-FOL and conclusion-FOL columns, or context and
statement. For plain propositional inputs, set input_format to logic. A logic
column can also contain a JSON object with premises and query as prefix arrays.
Example formula: forall x (Young(x) -> Smart(x)); query: Smart(Bob).
Unbound x, y and z in premises are universal variables; query variables must be
quantified. Separate formulas with a newline or semicolon.
Labels: label, gold, answer or flag. Without labels, accuracy is unavailable.
Optional mode: classical, cwa or causal. Classical is the default; known dataset
metadata and causal wording can also select the appropriate mode.

The final cell displays accuracy, precision, recall, F1 and the confusion matrix
when labels are supplied. It always displays runtime and failure counts.
It writes submission/submission.csv (id,flag), preserving input IDs and row order.
Detailed results and metrics: data/outputs/ai-assignment-evaluation/.
Paths are relative to the parent of submission/.

Included submission.csv: 532 public validation predictions, 479 correct (90.04%).
No private test data was available.
