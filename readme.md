```markdown
# DDJ-Reorder-JCA  (Dao De Jing Semantic Reordering)

## 1. 项目概述  Overview
本仓库提供《道德经》81章“段心提取→语义问句→TF-IDF余弦平滑重排”的完整可复现流程，
目标期刊：Journal of Cultural Analytics (JCA) / Digital Scholarship in the Humanities (DSH)。
- 零人工增删原文，仅用 permutation 提升相邻语义连贯性 8%
- Kendall τ 从 1.000 → 0.878，断点数 = 0
- 全代码 + 数据 + Notebook 一键 Open in Colab

## 2. 文件结构  File Structure
```
.
├── data/                          # 原始 & 中间数据
│   ├── yao_question_bank_81_en.tsv   # 双语段心 + 尹喜问句 (英文列名)
│   ├── core_sentences_81.tsv         # 仅段心结果
│   ├── semantic_reorder_index.csv    # 重排索引 (new_order)
│   └── kendall_smooth_final.csv      # 评价结果 A/B/C 三组
├── code/
│   ├── bilingual_notebook.ipynb      # 主流程（双语注释）
│   └── requirements.txt              # 依赖列表
├── out/
│   ├── V1_original.txt               # 原版
│   ├── V2_with_question.txt          # 补问未重排
│   └── V3_reordered_embedded.txt     # 补问 + 重排
└── README.md                         # 本文件
```

## 3. 一键复现  Reproducibility
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USER/DDJ-Reorder-JCA/blob/main/code/bilingual_notebook.ipynb)

1. 点击上方按钮 → 在 Google Colab 打开
2. Runtime → Run all  (≈ 3 min 完成)
3. 输出文件自动保存在 `/content/out/` 可下载

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
```bibtex
@data{ddj-reorder-2025,
  author = {Yang, B.},
  title  = {Dao De Jing Semantic Reordering Dataset},
  year   = {2025},
  doi    = {10.XXXX/zenodo.XXXXXXX},   # 待正式 DOI
  url    = {https://github.com/YOUR_USER/DDJ-Reorder-JCA}
}
```

## 7. 许可证  License
MIT © 2025 btsyang  
允许学术与商业再利用，须保留作者及出处信息。

## 8. 联系方式  Contact
Issue 或 PR 欢迎；邮箱：btsyang@qq.com
```