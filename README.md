# LiteratureRecommendationSystem

**简体中文** | [English](README.en.md)

基于 Django 的科技文献推荐课程项目，包含用户与文献界面，以及使用 PyTorch 向量和 FAISS 的推荐原型。当前代码需要补齐配置后才能在新环境运行。

## 环境要求

Python、MySQL；requirements.txt 仅包含 Django 4.2.9 和 Pillow。推荐模块另需兼容的 PyTorch、FAISS 与完整文章数据。

## 获取仓库

```bash
git clone https://github.com/RoxyXu151/LiteratureRecommendationSystem.git
cd LiteratureRecommendationSystem
```

私有仓库需要先通过 GitHub 认证。以下相对路径与操作均以本仓库为起点。

## 安装与启动

```bash
python -m venv .venv
# 先激活虚拟环境。
python -m pip install -r requirements.txt
```

PowerShell：`.venv\Scripts\Activate.ps1`；Linux/macOS：`source .venv/bin/activate`。

## 配置与准备

manage.py、system/settings.py 和 WSGI 配置仍引用旧模块名 day16，但当前配置包名为 system。运行前需统一这些模块路径，并配置 MySQL 数据库及驱动；README 更新不代表已修复这些代码问题。

## 使用方法与产物

完成配置修正后再执行 python manage.py migrate、python manage.py createsuperuser 和 python manage.py runserver，访问本地 8000 端口。deploy/deploy.py 通过相对路径读取文章 CSV 与两份向量文件，须从匹配目录运行，并保持文章和向量 ID 一致。

## 仓库导览

- [manage.py](manage.py)
- [system](system)
- [app01](app01)
- [deploy](deploy)
- [requirements.txt](requirements.txt)
- [原有详细资料](README.reference.md)：保留历史设计、截图和说明；涉及启动配置时以上述核对说明为准。

## 验证与常见问题

配置完成后执行 python manage.py check，再人工验证登录、文献页面与推荐数据加载。当前没有可证明完整性的测试报告；缺少 articles.csv 或额外依赖时推荐模块无法独立启动。

## 维护与贡献

修改功能或使用方式时同步更新中英文 README。问题反馈请附复现步骤、环境版本与去除敏感信息后的日志；提交改动时说明实际完成的验证。

## 许可与来源

许可条款以仓库的 [LICENSE](LICENSE) 为准。第三方代码、数据、模型、论文与素材保留各自的许可和署名。
