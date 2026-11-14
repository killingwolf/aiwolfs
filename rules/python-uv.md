# Python 工具链（强制）

- 所有 Python 项目一律用 uv 作为唯一的项目 / 依赖 / 虚拟环境管理工具；
  禁止用 pip、poetry、pipenv、conda 安装依赖或创建环境。
- 新建项目：`uv init`；添加依赖：`uv add <pkg>`；移除依赖：`uv remove <pkg>`；同步环境：`uv sync`。
- 运行任何 Python 命令一律经 `uv run`（如 `uv run python main.py`、`uv run pytest`），
  不要手动 activate 虚拟环境或直接调用裸 python / pip。
- 临时脚本依赖：`uv run --with <pkg> script.py`。
- 安装全局 CLI 工具：`uv tool install <pkg>`（不要用 pipx / pip install --user）。
- 生成或修改 pyproject.toml 时保持 uv 兼容结构，不写 poetry / pipenv 专属配置段。
- 机器上没有 uv 时先安装再继续：
  - Linux / macOS：`curl -LsSf https://astral.sh/uv/install.sh | sh`
  - Windows（PowerShell）：`powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"`
