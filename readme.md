# DDJ-Reorder-JCA  (Dao De Jing Semantic Reordering)

## 1. 项目概述  Overview
本仓库提供《道德经》81章“段心提取→语义问句→TF-IDF余弦平滑重排”的完整可复现流程，
目标期刊：Journal of Cultural Analytics (JCA) / Digital Scholarship in the Humanities (DSH)。
- 零人工增删原文，仅用 permutation 提升相邻语义连贯性 8%
- Kendall τ 从 1.000 → 0.878，断点数 = 0
- 全代码 + 数据 + Notebook 一键 Open in Colab

## 2. 文件结构  File Structure
```
- `code/bilingual_notebook.ipynb` – 完整流程（6 组评估 + 对齐余弦）
- `data/evaluation_6groups_aligned.csv` – 对齐后的 6 组平滑度与相邻余弦
- `out/V*_final.txt` – 6 份终版文本（重排后）
- `requirements.txt` – Python 依赖
```

## 3. 一键复现  Reproducibility
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17618725.svg)](https://doi.org/10.5281/zenodo.17618725)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USER/DDJ-Reorder-JCA/blob/main/code/bilingual_notebook.ipynb)[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17618725.svg)](https://doi.org/10.5281/zenodo.17618725)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bntsyang/DDJ-Reorder-JCA/blob/main/code/bilingual_notebook.ipynb)

## 4. 本地运行  Local Run

```bash
git clone https://github.com/YOUR_USER/DDJ-Reorder-JCA.git
cd DDJ-Reorder-JCA
python -m venv venv && source venv/bin/activate
pip install -r code/requirements.txt
jupyter notebook code/bilingual_notebook.ipynb
# 顺序运行全部单元即可
```

## 5. 关键结果  Key Results
| Group | Kendall τ | Char-co-occurrence | Artificial breaks |
|-------|-----------|--------------------|-------------------|
| A (canonical) | 1.000 | 0.143 | 0 |
| B (aug only)  | 1.000 | 0.130 | 0 |
| C (aug+reorder)| 0.878 | 0.132 | 0 |

- 重排提升相邻共现 +8%（相对）
- 零插入/删除/改写

## 6. 引用  Citation
若使用本数据或代码，请引用：
If you use this dataset or code, please cite:
```bibtex
@software{ddj_reorder_2025,
  author = {Yang, B.},
  title  = {DDJ-Reorder-JCA: Semantic Reordering of the Dao De Jing},
  year   = {2025},
  doi    = {10.5281/zenodo.17618725},
  url    = {https://github.com/btsyang/DDJ-Reorder-JCA}
}
```

## 7. 许可证  License
MIT © 2025 btsyang  
允许学术与商业再利用，须保留作者及出处信息。

## 8. 联系方式  Contact
Issue 或 PR 欢迎；邮箱：btsyang@qq.com
```