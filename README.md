# Network Security Audit & Vulnerability Assessment: TP-Link TD-W8968 Gateway

## 📌 Executive Summary
В данном проекте проведен аудит безопасности и тестирование на проникновение (Penetration Testing) физического сетевого шлюза **TP-Link TD-W8968** в локальном сегменте сети. 

Аудит выполнялся с хостовой машины Windows 10 без использования специализированных виртуальных сред. В ходе исследования выявлен **Высокий уровень риска (High Risk)**, обусловленный наличием устаревших сетевых служб и потенциальной устойчивостью к бинарным эксплойтам.

---

## 🛠 Target & Environment
* **Target Device:** TP-Link TD-W8968 Home Gateway (`192.168.2.1`)
* **Target MAC:** `1C:3B:F3:0B:EB:F0`
* **Auditor System:** Windows 10 Host (`192.168.2.113`, Wi-Fi)
* **Tooling:** Nmap 7.991, Windows PowerShell, OpenSSH Client

---

## 🔍 Audit Methodology & Steps

### 1. Reconnaissance & Service Enumeration
Проведено сканирование сетевых портов и определение версий запущенных служб:
```powershell
nmap -p 22,53,80,1900 -sV 192.168.2.1
