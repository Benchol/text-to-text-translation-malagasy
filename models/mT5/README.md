# Détection de discours haineux en malgache avec mT5

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Modèle de classification fine-tuné pour identifier les discours haineux en langue malgache à partir de posts Facebook.

## Fonctionnalités principales

- 🚀 **Modèle basé sur mT5-small** fine-tuné
- ⚖️ **Gestion du déséquilibre** (32.5% de haineux) via Focal Loss
- 📊 **Métriques complètes** : Accuracy, Précision, Recall, F1, ROC-AUC
- 📈 **Visualisations** : Matrices de confusion, courbes ROC/Precision-Recall
- 💾 **Sauvegarde/Restauration** des modèles

## Architecture technique

```python
MT5Encoder → Mean Pooling → Classifieur (512 → 256 → 2) → Focal Loss
```

## Exemples d'utilisation

```bash
#!/bin/bash
python finetuning_mt5.py \
    --train_file_id FILE_TRAIN_ID \
    --test_file_id FILE_TEST_ID \
    --batch_size BATCH_SIZE \
    --epochs EPOCH \
    --learning_rate LEARNING_RATE \
    --wandb_project WANDB_PROJECT \
    --wandb_name WANDB_NAME \
    --wandb_key WANDB_KEY
```
