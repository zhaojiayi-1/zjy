# 操作手册：基于jsPsych的颜色识别实验

## 介绍

本文档详细描述了如何设置、运行和理解一个基于jsPsych库的简单颜色识别实验。实验涉及参与者对屏幕上显示的蓝色或橙色圆圈做出反应。

## 环境要求

1. **浏览器**：最新版本的Google Chrome、Firefox或其他支持HTML5和JavaScript的浏览器。
2. **jsPsych库**：包括核心库和所需的插件。
3. **图像文件**：包括`blue.png`和`orange.png`。

## 文件结构

project_folder/
│
├── index.html (即本文件)
├── jspsych-6.3.1/
│ ├── jspsych.js
│ ├── plugins/
│ ├── jspsych-html-keyboard-response.js
│ ├── jspsych-image-keyboard-response.js
├── img/
│ ├── blue.png
│ ├── orange.png

## 详细步骤

### 1. 设置HTML页面

1. 创建一个新的HTML文件，命名为`index.html`。
2. 在HTML文件的头部（`<head>`标签内），引入jsPsych库和所需插件。
3. 在HTML文件的样式部分，使用flexbox设置页面布局和样式。
4. 在HTML文件的主体部分（`<body>`标签内），创建一个容器用于显示实验内容，包括欢迎信息和实验说明。

### 2. 编写JavaScript代码

1. 创建一个`timeline`数组，用于存储实验的各个步骤。
2. 添加欢迎信息步骤，类型为`html-keyboard-response`，提示按任意键开始实验。
3. 添加实验说明步骤，类型为`html-keyboard-response`，解释实验任务和按键要求。
4. 定义实验中使用的图片刺激（蓝色和橙色圆圈），并将其随机重复多次以形成试验序列。
5. 定义一个固定十字步骤，作为每次试验的起始注视点，持续1秒钟。
6. 定义试验步骤，显示蓝色或橙色圆圈，并记录参与者的反应。
7. 将所有试验步骤添加到`timeline`数组中。

### 3. 初始化实验

1. 使用`jsPsych.init`函数初始化实验，传入`timeline`数组。
2. 设置实验结束后的回调函数，显示实验数据。

### 4. 运行实验

1. **准备环境**：
   - 确保所有文件都在正确的目录中。
   - 使用支持HTML5和JavaScript的浏览器打开`index.html`文件。

2. **启动实验**：
   - 打开`index.html`后，页面会显示欢迎信息，按任意键开始实验。
   - 阅读说明，了解实验内容。

3. **参与实验**：
   - 当圆圈出现时，根据颜色迅速按下对应的键（蓝色按`F`，橙色按`J`）。
   - 实验自动记录反应时间和正确性。

4. **查看结果**：
   - 实验结束后，结果会自动显示在页面上。

## 注意事项

1. **图像路径**：确保`blue.png`和`orange.png`在`img`文件夹中，并且路径正确。
2. **反应时间**：实验的反应时间会影响结果的准确性，确保参与者在无干扰的环境中进行实验。

## 修改实验

如需修改实验，请参考以下步骤：

- **修改试验次数**：修改`jsPsych.randomization.repeat(test_stimuli, 30);`中的30为所需的试验次数。
- **修改颜色和按键对应关系**：修改`instructions`和`test_stimuli`中颜色和按键的说明。

通过本文档，您可以成功设置、运行和理解一个简单的颜色识别实验。如有其他问题，请参考[jsPsych文档](https://www.jspsych.org/)或联系相关技术支持。
