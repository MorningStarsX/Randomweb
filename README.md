# **Randomweb**
## 网页权重抽人器＋抽奖转盘
## 效果: [Randomweb](https://morningstarsx.github.io/Randomweb/)
## *权重抽取原理*
1. **权重随机抽取**：每个名字有一个权重（初始 1.0），通过 `weightedPickOnce` 按权重比例随机抽取（累积权重后取随机数）。
2. **冷却机制**：抽中的人进入冷却状态（默认 30 秒），冷却期间不可再被抽中（`getEligibleList` 会过滤掉）。
3. **降权机制**：抽中后权重乘以 `multiplier`（默认 0.4），降低再次被抽中的概率。
4. **单次多抽**：`pickMultiple(count)` 循环抽取 count 次，每次从临时名单移除已抽中的人，避免同批重复。
## 抽取流程（doDraw）
用户点"开始抽取" → 读取人数 → 校验 → 显示动画弹窗 → `animateAndPick`（轮盘/滚动动画）→ `pickSimulated` 抽选 → `applyPickedResults` 降权+设冷却 → 保存历史 → 显示结果弹窗。
### *By_MorningStarsX*

---

## 如何使用

### [1]Fork项目

#### 1.替换默认名单
- 文件路径
   ```
   web/index.html
   ```
   查找
   ```
   const DEFAULT_LIST = {.....}
   ```
   替换.
 >Fork前给个Star吧

#### 2.Push Pages
- 在`Actons`---`Deploy Static Web to GitHub Pages`中选择`Run workflow`
>请确保您Github中的Pages功能开启

### [2]下载HTML文件本地运行
- 文件路径
   ```
   web/index.html
   ```
   进入该文件点击下载按钮
- 按照`替换默认名单`步骤进行

---

>部分代码使用AI,请理性对待