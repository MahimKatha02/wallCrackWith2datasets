# Phase-6 Protocol — Multidataset Wall Crack Segmentation

Created (UTC): 2026-03-30T17:29:25Z

## 1) Scope
We evaluate pixel-level crack segmentation models trained using PyTorch + segmentation-models-pytorch (SMP) with EfficientNet-B3 encoders.
All models must be evaluated on the **same exact split CSVs**, and split hashes are recorded for reproducibility.

## 2) Data splits (frozen)
- train_split.csv SHA256: 9c02ef25f7cd668418a76fd556d0a8886258eaa7f6418f1859d6682fb8e2065f
- val_split.csv   SHA256: e77305c80edf1a524274874537ef034d081a5047da0f23354cd94a85f73e8ccd

Counts:
- Train samples: 9603
  - crack-present: 8367
  - no-crack: 1236
  - rule used: has_crack = has_crack
- Val samples: 1695
  - crack-present: 1477
  - no-crack: 218
  - rule used: has_crack = has_crack

## 3) Preprocessing (must match pretrained encoder)
If an encoder uses ImageNet pretrained weights, preprocessing must match the encoder's pretraining preprocessing.
SMP explicitly recommends preparing data “the same way as during weights pretraining” using `get_preprocessing_fn`.
Reference: SMP documentation (Quick Start).

## 4) Metrics (binary segmentation)
Let GT mask be A and predicted mask be B (binary sets of crack pixels).

### IoU (Jaccard / Intersection-over-Union)
IoU = |A ∩ B| / |A ∪ B|.

**Empty-aware IoU (required):**
- if A empty and B empty => IoU = 1
- if A empty and B non-empty => IoU = 0
- else IoU = |A ∩ B| / |A ∪ B|

### Dice (Sørensen–Dice)
Dice = 2|A ∩ B| / (|A| + |B|).
Use empty-aware handling consistent with IoU:
- if A empty and B empty => Dice = 1
- if A empty and B non-empty => Dice = 0
- else standard Dice.

### Crack-only vs Overall reporting (required)
Because cracks are thin and pixel-imbalanced:
- Report **overall** (all val images)
- Report **crack-only** (subset where GT has crack pixels)

### No-crack false positive rate (required)
On no-crack GT images (GT empty):
- FP if predicted mask has any positive pixels (pred_any = True)
- FP rate = FP_count / N_no_crack

### Pixel precision–recall AUC (required)
Compute pixel-level PR curve from sampled pixels using scikit-learn:
- `precision_recall_curve(y_true, y_score)`
- AUC computed over the PR curve points

Sampling:
- Use a fixed pixel sampling budget (e.g., 300,000 pixels) with deterministic seed.
- Store sampled size and seed in outputs.

## 5) Threshold policy
Baseline threshold for artifact parity: **0.5**.
Later (Phase-8), we will tune thresholds and publish `threshold_policy.json`.

## 6) Output naming convention (frozen)
All models must write the same artifact set with consistent prefixes, e.g.:
- *_val_metrics.csv
- *_val_summary_report.csv
- *_val_pr_auc_pixel.csv, *_pixel_pr_curve.png
- *_val_iou_hist_all.png, *_val_iou_hist_crack_only.png
- *_confidence_mean_pred_hist.png, *_confidence_p95_hist.png (p95 over predicted pixels only)
- *_gt_crack_area_hist.png, *_pred_crack_area_hist.png
- *_bbox_obb_overlays.png
- *_topk_worst_gallery.png, *_topk_worst_crack_only_gallery.png

## References (implementation guidance)
- SMP preprocessing recommendation (`get_preprocessing_fn`): https://segmentation-modelspytorch.readthedocs.io/ (Quick Start)
- scikit-learn PR curve: https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_recall_curve.html
- Jaccard/IoU definition: https://en.wikipedia.org/wiki/Jaccard_index
- Dice definition: https://en.wikipedia.org/wiki/Dice-S%C3%B8rensen_coefficient
