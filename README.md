# [ EaseFilter Secure Sandbox SDK & Tools](https://www.easefilter.com/Forums_Files/Secure-Sandbox.htm)
A robust, enterprise-grade file security, process monitoring, and sandboxing framework built on top of Windows file system filter drivers. **EaseFilter Secure Sandbox** provides a tightly controlled, isolated environment to run untrusted applications, prevent malware and ransomware outbreaks, protect confidential data, and enforce strict Zero Trust access control policies.
![Secure Sandbox Architecture](https://www.easefilter.com/Images/secure-sandbox-architecture.jpg)

## 🚀 Key Features

* **Advanced Process Isolation:** Restrict the permissions of untrusted Windows executables (`.exe`, scripts) to prevent unauthorized system modifications.
* **Malware & Ransomware Prevention:** Automatically intercept execution requests from vulnerable directories (such as browser download paths or temporary folders) to stop zero-day threats and malicious attachments.
* **Granular File Access Control:** Define least-privilege access rights per folder and process, restricting unauthorized processes from reading or altering sensitive files.
* **Transparent File Encryption:** Automatically encrypt confidential files within sandbox boundaries, preventing unauthorized data exfiltration or distribution outside corporate environments.
* **Registry Protection:** Lock down critical Windows registry hives to prevent untrusted binaries from making persistent system-level changes.
* **Multi-Language SDK Support:** Integrates seamlessly into enterprise applications via C#, C++, Python, Java, Go, and Rust APIs.

---

## 🛠️ Architecture & How It Works

EaseFilter Secure Sandbox operates at the kernel level using the **Windows Minifilter Driver Framework**. It intercepts I/O request packets (IRPs) directly above the file system before they reach their target storage volume.

1. **Interception:** Captures file system operations, process creation requests, and registry modifications in real time.
2. **Policy Enforcement:** Evaluates process trust levels and matching filter masks (e.g., `C:\Sandbox\*`) against defined access rules.
3. **Action & Remediation:** Allows, logs, modifies, or blocks operations instantly (e.g., blocking write access to protected directories or denying execution of untrusted binaries).

---

## 📋 Configuration Guide

### 1. Restricting Executable Binaries
* Configure sandbox folder filter masks (e.g., `C:\Sandbox\*`).
* Enable or disable execution permissions to test untrusted applications safely without risking your underlying operating system or setting up cumbersome virtual machines.
* Configure fine-grained access rights (e.g., allow read-only access to `C:\Windows` while granting full rights to `C:\MySandbox`).

### 2. Protecting Confidential Files
* Designate protected folders (e.g., `C:\ProtectedFolder\*`).
* Apply least-privilege default rules so only verified, authorized processes (such as those launched from trusted system directories) can interact with sensitive data.
* Enable transparent encryption to secure data at rest.

---


## EaseFilter File System Filter Driver SDK Reference
| Product Name | Description |
| --- | --- |
| [Cloud File System SDK](https://www.easefilter.com/cloud/cloud-file-system-sdk.htm) | EaseFilter Cloud File System SDK Introduction. |
| [CloudTier Storage Tiering SDK](https://www.easefilter.com/cloud/storage-tiering-sdk.htm) | EaseFilter Storage Tiering Filter Driver SDK Introduction. |
| [File Monitor SDK](https://www.easefilter.com/kb/file-monitor-filter-driver-sdk.htm) | EaseFilter File Monitor Filter Driver SDK Introduction. |
| [File Control SDK](https://www.easefilter.com/kb/file-control-file-security-sdk.htm) | EaseFilter File Control Filter Driver SDK Introduction. |
| [File Encryption SDK](https://www.easefilter.com/kb/transparent-file-encryption-filter-driver-sdk.htm) | EaseFilter Transparent File Encryption Filter Driver SDK Introduction. |
| [Registry Filter SDK](https://www.easefilter.com/kb/registry-filter-drive-sdk.htm) | EaseFilter Registry Filter Driver SDK Introduction. |
| [Process Filter SDK](https://www.easefilter.com/kb/process-filter-driver-sdk.htm) | EaseFilter Process Filter Driver SDK Introduction. |
| [EaseFilter SDK Programming](https://www.easefilter.com/kb/programming.htm) | EaseFilter Filter Driver SDK Programming. |

## EaseFilter SDK Sample Projects
| Sample Project | Description |
| --- | --- |
| [CloudTier Storage Tiering Demo](https://www.easefilter.com/cloud/cloudtier-storage-tiering-demo.htm) | A HSM File System Filter Driver Demo. |
| [CloudTier S3 Tiering Demo](https://www.easefilter.com/cloud/cloudtier-s3-intelligent-tiering-demo.htm) | CloudTier S3 Intelligent Tiering Demo. |
| [Cloud File DR S3 Demo](https://www.easefilter.com/cloud/cloud-file-dr-demo.htm) | Cloud File DR S3 Demo. |
| [Amazon S3 File Explorer Demo](https://www.easefilter.com/cloud/s3-browser-demo.htm) | Amazon S3 File Explorer Demo. |
| [Auto File DRM Encryption](https://www.easefilter.com/kb/auto-file-drm-encryption-tool.htm) | Auto file encryption with DRM data embedded. |
| [Transparent File Encrypt](https://www.easefilter.com/kb/AutoFileEncryption.htm) | Transparent on access file encryption. |
| [Secure File Sharing with DRM](https://www.easefilter.com/kb/DRM_Secure_File_Sharing.htm) | Secure encrypted file sharing with digital rights management. |
| [File Monitor Example](https://www.easefilter.com/kb/file-monitor-demo.htm) | Monitor file system I/O in real time, tracking file changes. |
| [File Protector Example](https://www.easefilter.com/kb/file-protector-demo.htm) | Prevent sensitive files from being accessed by unauthorized users or processes. |
| [FolderLocker Example](https://www.easefilter.com/kb/FolderLocker.htm) | Lock file automatically in a FolderLocker. |
| [Process Monitor](https://www.easefilter.com/kb/Process-Monitor.htm) | Monitor the process creation and termination, block unauthorized process running. |
| [Registry Monitor](https://www.easefilter.com/kb/RegMon.htm) | Monitor the Registry activities, block the modification of the Registry keys. |
| [Secure Sandbox Example](https://www.easefilter.com/kb/Secure-Sandbox.htm) |A secure sandbox example, block the processes accessing the files out of the box. |
| [FileSystemWatcher Example](https://www.easefilter.com/kb/FileSystemWatcher.htm) | File system watcher, logging the file I/O events. |
| [ZeroTrust Example](https://www.easefilter.com/kb/zero-trust-file-access-control-demo.htm) | Zero trust file access control with encryption feature. |

## Filter Driver Reference

* [Understand MiniFilter Driver](https://www.easefilter.com/kb/understand-minifilter.htm)
* [Understand File I/O](https://www.easefilter.com/kb/File_IO.htm)
* [Understand I/O Request Packets(IRPs)](https://www.easefilter.com/kb/understand-irps.htm)
* [Filter Driver Developer Guide](https://www.easefilter.com/kb/DeveloperGuide.htm)
* [MiniFilter Filter Driver Framework](https://www.easefilter.com/kb/minifilter-framework.htm)
* [Isolation Filter Driver](https://www.easefilter.com/kb/Isolation_Filter_Driver.htm)

## License

This repository contains two distinct licensing categories:

1. **Wrapper/Implementation Code (MIT License):** 
   The source code, scripts, and configuration files provided directly in this repository are licensed under the [MIT License](LICENSE). You are free to modify, distribute, and use this specific integration code.

2. **EaseFilter SDK (Commercial License):**
   This project requires the EaseFilter SDK (including its binaries, filter drivers, and core libraries) to function. The EaseFilter SDK is **proprietary commercial software** and is strictly excluded from the MIT License.   
   To use the EaseFilter SDK for commercial purposes or in a production environment, you must obtain a valid commercial license directly from [EaseFilter](https://www.easefilter.com/license.pdf).

## Support
If you have questions or need help, please contact support@easefilter.com 

[Home](https://www.easefilter.com/) | [Solution](https://www.easefilter.com/solutions.htm) | [Download](https://www.easefilter.com/download.htm) | [Demos](https://www.easefilter.com/online-fileio-test.aspx) | [Blog](https://blog.easefilter.com/) | [Programming](https://www.easefilter.com/kb/programming.htm)
