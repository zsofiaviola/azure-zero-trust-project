# azure-zero-trust-project
End-to-end Azure Zero Trust architecture with Hub-Spoke networking, NSGs, Key Vault integration and a protected App Service deployment.
---

## Project Overview

This project demonstrates a **Zero Trust–aligned Azure architecture**, built completely from scratch and deployed step-by-step in a real cloud environment.

The solution includes:

- Isolated **Hub & Spoke** VNets  
- Segmented **Web / App / DB** subnets  
- Strict **NSG (Network Security Group)** policies  
- Secure **VNet Peering**  
- **Azure Key Vault** with managed identity access  
- A running **Azure App Service (Python)**  
- Fully private network paths (App and DB not exposed to the internet)

The focus is on secure cloud architecture, network segmentation, identity-based access, and troubleshooting real-world App Service deployments.

---

## Architecture Overview

### **Hub–Spoke Virtual Network Model**
- `vnet-hub` – central routing & VNet peering  
- `vnet-web`, `vnet-app`, `vnet-db` – isolated spoke tiers following Zero Trust separation  

### **Strict NSG Rules**
- Allow **Web → App** (TCP 8080)  
- Allow **App → DB** (TCP 3306)  
- Block all outbound internet from App/DB tiers  
- Deny all unnecessary east–west movement  

### **Azure Key Vault**
- Access controlled via **Managed Identity**  
- No public access  
- Secrets retrievable only through **RBAC**  

### **Python App Service**
- Secure deployment  
- Runs in an Azure-managed Linux environment  
- Deployment verified using **Kudu**, container logs and debugging  

---

## Core Azure Components

| Component | Purpose |
|----------|---------|
| **VNet Hub** | Central network, peering management |
| **Spoke VNets (Web/App/DB)** | Tiered isolation following Zero Trust |
| **NSGs** | Enforce least privilege communication |
| **Azure Key Vault** | Secure secret storage via MI |
| **App Service** | Python Web App (Hello Azure App Service) |
| **App Service Plan** | Linux hosting |

---

## Zero Trust Principles Implemented

- No implicit trust between network tiers  
- Only required ports allowed  
- Outbound internet blocked where unnecessary  
- Key Vault access restricted to managed identity only  
- Hub-and-spoke segmentation  
- Continuous validation through **logs**, **SSH**, and **Kudu**  

---

## Troubleshooting & Fixes (Real-World Issues)

This project included intentional and unintentional real-world debugging, demonstrating practical problem-solving skills:

- Missing **wwwroot** folder → manually recreated  
- SSH & Kudu connection failures → resolved by correcting App Service runtime  
- App Service ignoring deployment → fixed via clean rewrite of directory structure  
- NSG and routing conflicts → validated and corrected  
- Key Vault identity not recognized → configured properly with Access Policies / RBAC  

These steps show **hands-on experience** with Azure’s behavior under real error conditions.

---

## Result

A fully functioning, secure, Zero Trust–inspired architecture with:

- Running Python App Service  
- Correct network segmentation  
- Working Key Vault integration  
- Proper NSG enforcement  
- Clean, well-structured Azure deployment  

---

## About This Project

Created as part of my personal cloud security journey.

Focus areas include:

- Azure networking  
- Zero Trust architecture  
- Identity and access security  
- Secure application hosting  

---

## Why This Project Matters

This architecture reflects real enterprise cloud patterns:

- Hub–spoke network topologies  
- Least privilege segmentation  
- Identity-based secret access  
- Secure workload isolation at scale  

It showcases my ability to **design, deploy, break, fix, document, and complete** a professional Azure security-focused environment.

---

**Created by:**  
### **Zsofia Viola Szabo**
