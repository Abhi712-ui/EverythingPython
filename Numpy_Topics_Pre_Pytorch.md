Here is the NumPy checklist to finish before PyTorch.

# Core

* Array fundamentals: `ndarray`, rank vs shape, `itemsize`, `ndim`, `size`.
* Dtypes: `bool`, integer sizes, `float32/64`, `complex64/128`; casting with `astype`, promotion rules.
* Array creation: `array`, `asarray`, `zeros/ones/full/empty`, `arange/linspace/logspace`, `eye/identity`, `diag`.
* Indexing and slicing: basic slices are views; integer vs boolean indexing (copies); `np.newaxis/None`, `...` (ellipsis); `take`, `put`, `where`.
* Broadcasting: rules (align trailing axes; sizes equal or 1), `expand_dims`, `squeeze`, `np.broadcast_to`.
* Vectorized ops and ufuncs: elementwise ops, `out=` parameter, `reduce/accumulate/outer/at`.
* Reductions and aggregations: `sum/mean/prod/min/max`, `argmin/argmax`, `any/all`, `keepdims`, `axis`.
* NaN-aware ops: `nan*` variants (`nanmean`, `nansum`, etc.), `isnan/isfinite/isinf`, `isclose/allclose`.
* Shape manipulation: `reshape`, `ravel/flatten`, `transpose`, `swapaxes`, `moveaxis`, `expand_dims`, `squeeze`.
* Join and split: `concatenate`, `stack`, `hstack/vstack`, `column_stack`, `split/array_split`.
* Sorting and selection: `sort`, `argsort`, `lexsort`, `partition/argpartition`, `unique`, `bincount`, `histogram`.
* Linear algebra essentials: `@`/`matmul`, `dot`, `einsum`, `tensordot`, `outer/inner`; `linalg.solve`, `inv`, `pinv`, `svd`, `eigh/eig`, `qr`, `cholesky`, `norm`, `matrix_rank`.
* Random generation (Generator API): `np.random.default_rng`, seeding, `integers`, `uniform`, `normal`, `choice`, `permutation`.
* Numerical stability helpers: `clip`, `log1p`, `expm1`, `logaddexp`, `finfo/eps`, `minimum/maximum`.
* Conditional logic: `where`, `select`, `piecewise`, masking patterns.
* Views vs copies: slicing views; fancy indexing copies; `copy()`, `np.ascontiguousarray`; `writeable` flag.
* Memory layout and strides: C- vs F-order, `strides`, `np.lib.stride_tricks.as_strided` (caution).
* In-place ops and performance: preallocation, avoid Python loops, broadcasting instead of `np.vectorize`, careful dtype choice, cache effects.
* I/O basics: `save/savez/savez_compressed`, `load`, `memmap`, `loadtxt/genfromtxt` (when needed).
* Printing and debugging: `set_printoptions`, inspecting shapes/dtypes quickly.

# Useful but Optional

* FFTs: `np.fft.*` (know they exist; PyTorch has its own).
* Polynomials: `np.polynomial.*` (rare in PyTorch workflows).
* Structured/record arrays and `datetime64/timedelta64` (not common for tensors).
* Sparse arrays (NumPy doesn’t natively; know ecosystem exists).

# Bridge to PyTorch (minimal interop you should know)

* Conversions: `torch.from_numpy(ndarray)` shares memory with CPU float/int arrays; `.numpy()` from CPU tensors.
* Contiguity: ensure contiguous before convert (`np.ascontiguousarray`); PyTorch prefers contiguous.
* Dtypes alignment: prefer `float32` defaults when prepping data.
* Broadcasting, reduction axes, and shape ops map closely; habits transfer.

If you want, I can turn this into a 2-week drill plan with exercises and quick checks per bullet.

---
Yes. It is the fastest path if you keep scope tight and ship artifacts.

# Plan

1. **Pick one scoped project**

   * **Vision:** CIFAR-10 classifier with data augmentation and a small ResNet.
   * **NLP:** IMDb or AG-News text classifier with an LSTM or a tiny Transformer.
   * **Tabular:** Titanic or a UCI dataset with an MLP and feature scaling.
     Choose one. One model, one metric, one dataset.

2. **PyTorch skills you will learn in-line**

   * Tensors, dtypes, device placement, AMP (`torch.cuda.amp`).
   * Autograd and manual training loop: forward → loss → `backward()` → `step()` → `zero_grad()`.
   * `nn.Module`, `nn.Sequential`, initialization, `state_dict`.
   * `DataLoader`, custom `Dataset`, `transforms`, batching, shuffling, num\_workers.
   * Optimizers and schedulers: SGD/Adam, weight decay, cosine/StepLR, early stopping.
   * Metrics and logging: accuracy/F1, loss curves, checkpointing, reproducible seeds.
   * Saving/loading models, exporting predictions, simple inference script.

3. **Four-phase execution (2–3 weeks)**

   * **Day 1–2:** Baseline. Load data. Simple model. Overfit a tiny batch on purpose. Establish a metric.
   * **Days 3–6:** Solid loop. Add validation split, early stopping, LR schedule, AMP. Hit a clean baseline.
   * **Days 7–12:** Improve. Better model, regularization (dropout, weight decay), augmentation, hyperparams.
   * **Days 13–14+:** Polish. Write `train.py`, `eval.py`, `inference.py`. Add README, figures, results table.

4. **Deliverables that read well on a resume**

   * Public repo with this structure:

     ```
     project/
       data/ (gitignored)
       src/
         datasets.py
         models.py
         train.py
         eval.py
         inference.py
         utils.py
       configs/
         default.yaml
       notebooks/
         00_exploration.ipynb
       results/
         metrics.csv
         curves.png
         confusion_matrix.png
       README.md
       requirements.txt
     ```

   * README must include: problem, data, model, metric, final score, how to run, key learnings.
   * A single figure: training/validation loss and accuracy. One confusion matrix for the final model.

5. **Minimum bar for “resume-worthy”**

   * Reproducible run command that completes on free Colab or a mid-range GPU.
   * Clear, labeled plots. Sensible ablation: show 2–3 changes and their metric deltas.
   * Clean code with type hints and docstrings. No hard-coded paths.

6. **Suggested stretch goals**

   * Simple hyperparameter search (Grid or Random).
   * Mixed precision speedup and a short timing table.
   * Export to TorchScript or `torch.save` with an `inference.py` CLI.

7. **Risk controls**

   * Scope creep: lock dataset and metric on day 1.
   * Compute limits: keep batch sizes small, use AMP, cache datasets.
   * Overfitting: use a fixed validation set, early stopping, and report test-set only once.

# Example resume bullets

* “Built and productionized a PyTorch CNN for CIFAR-10. +7.8 pp accuracy over baseline via augmentation, weight decay, and cosine LR; mixed-precision cut epoch time 38%. Reproducible CLI and docs.”
* “Implemented text classifier on AG-News in PyTorch. Replaced LSTM with 2-layer Transformer, improved test accuracy 3.1 pp; added early stopping and learning-rate warmup; full training script and ablations.”

If you tell me which track you choose, I will give you a dataset-specific checklist and a starter `train.py`.
