---
title: "GitHub - fastapi/fastapi-new: Create a new FastAPI project in one command"
url: https://github.com/fastapi/fastapi-new
tags: [programming, AI/ML]
category: Code Repository
date: 2025-11-11
id: 0FDA4686-D6D5-4EFE-97E8-156175B6BD71
created: 2025-11-11T12:30:11Z
modified: 2025-11-11T12:30:11Z
---
# GitHub - fastapi/fastapi-new: Create a new FastAPI project in one command

## Summary

Create a new FastAPI project in one command

**Category:** `Code Repository`  

**Tags:** `programming` `AI/ML`

**Source:** [https://github.com/fastapi/fastapi-new](https://github.com/fastapi/fastapi-new)

---

## Content

Repository: fastapi/fastapi-new
Description: Create a new FastAPI project in one command

⭐ Stars: 106
Language: Python

README:

# fastapi-new

Create a new FastAPI project in one command. ✨

<a href="https://github.com/fastapi/fastapi-new/actions?query=workflow%3ATest+event%3Apush+branch%3Amain" target="_blank">
    <img src="https://github.com/fastapi/fastapi-new/actions/workflows/test.yml/badge.svg?event=push&branch=main" alt="Test">
</a>
<a href="https://coverage-badge.samuelcolvin.workers.dev/redirect/fastapi/fastapi-new" target="_blank">
    <img src="https://coverage-badge.samuelcolvin.workers.dev/fastapi/fastapi-new.svg" alt="Coverage">
</a>
<a href="https://pypi.org/project/fastapi-new" target="_blank">
    <img src="https://img.shields.io/pypi/v/fastapi-new?color=%2334D058&label=pypi%20package" alt="Package version">
</a>
<a href="https://pypi.org/project/fastapi-new" target="_blank">
    <img src="https://img.shields.io/pypi/pyversions/fastapi-new.svg?color=%2334D058" alt="Supported Python versions">
</a>

## How to use

Install [uv](https://docs.astral.sh/uv/getting-started/installation/) following their guide for your system.

Run:

```bash
uvx fastapi-new awesomeapp
```

This will create a new project `awesomeapp` with a basic FastAPI app, configured with uv.

Enter the directory:

```bash
cd awesomeapp
```

Run the development server:

```bash
uv run fastapi dev
```

Open your browser and go to `http://localhost:8000` to see your new FastAPI app running! 🚀

### Existing directory

If you want to create a new FastAPI project in an existing directory, run the command without a project name:

```bash
uvx fastapi-new
```

## License

This project is licensed under the terms of the MIT license.

