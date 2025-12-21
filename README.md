# 🐙 Wyag — Write Yourself a Git (Python)

A **from-scratch implementation of a Git-like version control system** written in Python.  
This project reimplements core Git internals to deeply understand how Git stores data, tracks files, resolves references, and manages the staging area.

> **Wyag is not a wrapper around Git** — it directly reads and writes Git-compatible repository structures.

---

## 🚀 Motivation

Git is one of the most widely used tools in software engineering, yet its internal mechanics are often treated as a black box.  
This project was built to **demystify Git internals** by reimplementing them step by step:

- How Git stores objects (**blobs, trees, commits, tags**)
- How references and SHA resolution work
- How the index (staging area) tracks file state
- How `git status`, `git add`, and `git rm` actually function

---

## ✨ Features Implemented

### 📁 Repository & Objects

- `init` — create a Git-compatible repository
- Object storage using **SHA-1 hashing**
- Supported object types:
  - **Blob** — file contents
  - **Tree** — directory snapshots
  - **Commit** — repository state + metadata
  - **Tag** — annotated and lightweight tags

---

### 🗂 Index (Staging Area)

- Binary index file parsing (**DIRC format**)
- Tracks:
  - File metadata (`ctime`, `mtime`, inode, permissions)
  - Blob SHA-1
  - File paths
- Used to efficiently detect file changes

---

### ⚙️ Core Commands

- `add` — stage files by writing blobs and updating the index
- `rm` — remove files from the index and working tree
- `status` — detect:
  - modified files
  - staged changes
  - untracked files
- `rev-parse` — resolve:
  - branch names
  - tags
  - abbreviated SHAs
  - symbolic references

---

## 🧠 Key Concepts Demonstrated

- Content-addressable storage
- SHA-1 hashing and object identity
- Reference resolution and dereferencing
- Tree construction from the index
- Efficient file change detection using metadata
- Binary file parsing and struct packing
