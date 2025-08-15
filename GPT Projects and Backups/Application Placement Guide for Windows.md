# Placement Guide

# 🧰 Tools Placement Reference

This chart helps you decide which applications should live in `C:\Tools` versus being left in their default install locations.

| Application / Tool              | Portable / Moveable? | Custom Install Path Allowed? | Safe to Relocate? | Notes |
|--------------------------------|-----------------------|------------------------------|-------------------|-------|
| **Neovim**                     | ✅ Yes                | ✅ Yes                       | ✅ Yes            | Fully portable zip available |
| **jq**                         | ✅ Yes                | ✅ Yes                       | ✅ Yes            | Standalone `.exe` |
| **ripgrep**                    | ✅ Yes                | ✅ Yes                       | ✅ Yes            | Standalone CLI utility |
| **fd**                         | ✅ Yes                | ✅ Yes                       | ✅ Yes            | Portable CLI search |
| **Git**                        | ⚠️ Semi              | ✅ Yes                       | ✅ With care      | Install using custom path |
| **CPU-Z / AIDA64 / Speccy**    | ✅ Yes                | ✅ Yes                       | ✅ Yes            | Works well as standalone |
| **MSI Afterburner**            | ⚠️ Semi              | ✅ Yes                       | ⚠️ Cautiously     | May retain config; test first |
| **Wave Link**                  | ⚠️ Semi              | ✅ Yes                       | ⚠️ With config backup | Installer allows custom path but config is in `AppData` |
| **Ollama**                     | ⚠️ Semi              | ⚠️ Unknown                   | ⚠️ Check build    | Depends on install method |
| **Ryzen Master**               | ❌ No                 | ❌ No                        | ❌ No             | Requires system-level integration |
| **AMD Adrenalin**             | ❌ No                 | ❌ No                        | ❌ No             | Driver and overlay tightly integrated |
| **Realtek/NVIDIA Drivers**     | ❌ No                 | ❌ No                        | ❌ No             | Must remain where installed |
| **Steam Games / Battle.net**   | ❌ No                 | ✅ Yes (different drive)     | ❌ No             | Use game library folders instead |
| **Firefox / PIA / Edge**       | ❌ No                 | ⚠️ Sometimes                 | ❌ No             | Often stores state and registry entries |

tags: [system-setup, tools, ctools, portability]
