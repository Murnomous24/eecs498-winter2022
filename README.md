# EECS 498 / 598 学习仓库

Justin Johnson · Winter 2022 · Deep Learning for Computer Vision。

## 课程文档

- [课程日程与阅读材料](schedule.md)
- [A1：PyTorch 与 kNN](assignments/assignment1.md) · [源码与 Notebook](assignments/A1/)
- [A2：线性分类器与两层神经网络](assignments/assignment2.md) · [源码与 Notebook](assignments/A2/)
- [A3：全连接网络与卷积网络](assignments/assignment3.md) · [源码与 Notebook](assignments/A3/)
- [A4：目标检测](assignments/assignment4.md) · [源码与 Notebook](assignments/A4/)
- [A5：RNN、图像描述与 Transformer](assignments/assignment5.md) · [源码与 Notebook](assignments/A5/)
- [A6：生成模型、网络可视化与风格迁移](assignments/assignment6.md) · [源码与 Notebook](assignments/A6/)
- [Mini-project：图像分类、超分辨率与 NeRF](mini-project/project.md)

课程文档由原页面转换为 Markdown，保留正文、作业要求和参考链接；日期及提交要求是 2022 年课程的原始说明。

## 开始练习

进入对应的 `assignments/A1/`–`assignments/A6/` 目录，按说明在 Colab 或自己的 Python / PyTorch 环境中打开 Notebook。初始源码保留教学模板，尚未填写答案或运行训练。

## 版本控制范围

- 跟踪作业源码、Notebook、必需的小型输入数据和示例图片，以及 Markdown 课程文档。
- `slides/`、`papers/`、原始 ZIP、下载的数据集、模型权重、训练输出、缓存和虚拟环境保留在本地，由 `.gitignore` 排除。
- A5 的 `two_digit_op.json` 和 A6 的 `images/` 属于练习输入，随源码提交。
- Notebook 保留教学内容及课程要求的输出；不安装自动清除输出的提交钩子。
- `.gitattributes` 将文本换行统一为 LF，图片等二进制文件保持原样。

本地参考资料包括 25 份课件和 21 篇论文 PDF；它们没有纳入 Git，新克隆的仓库不包含这些文件。日程中的外部参考链接需要联网访问。

## 资料来源

- [官方课程日程的 Wayback 存档](https://web.archive.org/web/20260616092844/https://web.eecs.umich.edu/~justincj/teaching/eecs498/WI2022/schedule.html)
- A2–A6 的模板来自官方课程附件的历史存档。
- A1 的官方 ZIP 未被存档，模板来自 [nizne9/EECS498-WI22 的固定提交](https://github.com/nizne9/EECS498-WI22/tree/a4712f9738dbdd8272042588c9b15f8a03b3ef82/A1)。`knn.py` 的 9 个和 `pytorch101.py` 的 20 个待填写代码块均为空白；无法与失效的官方 ZIP 做逐字节比较。
