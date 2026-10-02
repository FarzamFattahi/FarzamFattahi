# Farzam Fattahi

I build practical computer-vision projects and document the data, experiments,
deployment decisions and limitations.

## Featured project: Construction-PPE detection

[**Explore the project →**](https://github.com/FarzamFattahi/object-detector)
 · [Download the models](https://github.com/FarzamFattahi/object-detector/releases/tag/v1.1.0)
 · [Learn how it works](https://github.com/FarzamFattahi/object-detector/blob/master/docs/START_HERE.md)

Fine-tuned YOLO11n on Construction-PPE, with a similarity-based dataset audit,
validation-only checkpoint selection, held-out evaluation and independent ONNX
deployment. The interactive dashboard compares reference labels with predictions.

![Actual dataset annotations beside model predictions](https://raw.githubusercontent.com/FarzamFattahi/object-detector/master/assets/ppe/test_preview.jpg)

| Held-out result | Measured value |
|---|---:|
| All 11 classes, mAP50 / mAP50–95 | 0.536 / 0.272 |
| Five worn-equipment classes, mAP50 | 0.807 |
| Person AP50, pretrained → fine-tuned | 0.719 → 0.831 |
| Warmed CPU median, PyTorch / ONNX | 74.8 / 57.7 ms |

Evaluated on 141 held-out images after cross-split similarity filtering.
Missing-equipment labels remain weak (mAP50 0.141); this is a research demo,
not a safety certification system. Timing is specific to the measured machine.

The repository includes training curves, full test predictions, examples of
failures, a model card, reproducible scripts and 53 passing tests with Windows
and Linux CI.

[Read the experiment](https://github.com/FarzamFattahi/object-detector/blob/master/docs/PPE_CASE_STUDY.md)
 · [Inspect the model card](https://github.com/FarzamFattahi/object-detector/blob/master/docs/PPE_MODEL_CARD.md)
