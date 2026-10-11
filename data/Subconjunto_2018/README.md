# Subconjunto_2018

Small, hand-picked subset of the [ISIC 2018 challenge](https://challenge.isic-archive.com/data/#2018) data, used as an
extra evaluation set. The images were left out of this repository because of file-size limits.

To run notebooks `02`–`05`, recreate this layout:

```
data/Subconjunto_2018/
├── images/     # ISIC_XXXXXXX.jpg   (dermoscopic images)
├── masks/      # ISIC_XXXXXXX.png   (ground-truth lesion masks)
└── list.csv    # image ids + melanoma label, no header
```

The pre-computed features for this subset are already included in [`../features/`](../features), so the
classification notebook (`05`) can be explored without the images.
