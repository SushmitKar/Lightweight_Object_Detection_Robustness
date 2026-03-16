# Evaluating the Robustness of Lightweight Object Detection Models Against Adversarial Noise in Traffic Camera Feeds

## 1. Abstract
(100–200 words: problem, method, key result, conclusion)

## 2. Introduction
- Why traffic-camera robustness matters
- Why lightweight models are used in deployment
- Why noise/adversarial corruption is a concern
- Scope of this study

## 3. Literature Review
- Robust object detection in adverse weather/noise
- Lightweight detectors (YOLOv5n/YOLOv8n/SSD-MobileNet)
- Corruption benchmarks and robustness metrics
- Gap this project addresses

## 4. Dataset
### 4.1 Primary Dataset
- COCO 2017 val split (traffic-relevant classes)
- Source links and license
- Selected classes: person, bicycle, car, motorcycle, bus, truck, traffic light, stop sign

### 4.2 Optional Extensions
- BDD100K (driving scenes)
- UA-DETRAC (traffic surveillance)

### 4.3 Data Preparation
- Filtering logic
- Number of images used
- Train/val/test handling (if applicable)

## 5. Problem Definition
Given an input traffic image \(x\), detector \(f_\theta\) predicts bounding boxes/classes.
We evaluate degradation under noise transform \(T_s\) at severity \(s\):
\[
x_s = T_s(x)
\]
Goal: quantify drop in detection quality from clean to noisy inputs.

## 6. Research Objectives & Hypotheses
- O1: Quantify robustness drop across noise types/severities.
- O2: Compare lightweight models under identical protocol.
- H1: Performance decreases monotonically with severity.
- H2: Motion blur/fog produce larger degradation than mild Gaussian noise.

## 7. Methodology
### 7.1 Models
- YOLOv8n
- YOLOv5n

### 7.2 Noise Simulation
- Gaussian noise (s=1,3,5)
- Motion blur (s=1,3,5)
- Fog (s=1,3,5)
- Rain streaks (s=1,3,5)

### 7.3 Experimental Protocol
- Evaluate clean baseline
- Evaluate each model on each noise profile
- Keep confidence/IoU thresholds fixed
- Use same image subset for fair comparison

## 8. Implementation Details (Python)
- Dependencies and versions
- Hardware (CPU/GPU)
- Random seed
- Script entrypoint and config file

## 9. Evaluation Metrics
- TP, FP, FN
- Precision
- Recall
- F1-score
- (Optional) mAP@0.5 and mAP@0.5:0.95

## 10. Experiments & Results
### 10.1 Clean Baseline
(Insert table)

### 10.2 Noise-wise Comparison
(Insert table and plot)

### 10.3 Severity-wise Degradation
(Insert plot and % drop table)

### 10.4 Per-class Effects
(If available, class-wise table)

## 11. Discussion
- Which model is most robust and why
- Which noise is most harmful
- Deployment implications for traffic monitoring

## 12. Limitations
- Synthetic noise vs real-world weather
- Dataset domain shift
- Detector/version dependence

## 13. Conclusion & Future Work
- Main findings
- Next steps: BDD100K/UA-DETRAC, adversarial attack methods, robustness training

## 14. References
- COCO dataset
- BDD100K docs
- UA-DETRAC site
- Model papers/docs

## 15. Appendix
- Commands used
- Config snapshot
- Additional figures/tables