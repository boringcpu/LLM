# LLM

## 安装uv
```text
pip install uv
```

## 创建项⽬环境
```text
# uv 创建虚拟环境(本教程以uv为例)
uv venv .venv-dataflow --python 3.10
# 激活环境
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv-dataflow\Scripts\Activate.ps1
```

## clone 项⽬源码安装
```text
# 克隆仓库到本地
git clone https://github.com/OpenDCAI/DataFlow.git
# 编译源码
cd DataFlow
$env:UV_HTTP_TIMEOUT = "300" # 防超时
uv pip install -e .
# 查看版本（能查看到版本表示安装成功）
dataflow -v
```

## demo数据集下载
```text
$env:HF_ENDPOINT = "https://hf-mirror.com"
hf download OpenDCAI/dataflow-demo-Reasoning --repo-type dataset --local-dir ./data
```

## 修改内容
```text
# 1. first_entry_file_name 填入 input.jsonl 正确的地址
first_entry_file_name =
"../example_data/ReasoningPipeline/pipeline_math_short.json",
# 2. answer_format_filter_step1 的 input_key 值改为 "instruction"
input_key = "output", # 改 input_key = "instruction",
# 3. answer_groundtruth_filter_step2 整个函数注释掉
```