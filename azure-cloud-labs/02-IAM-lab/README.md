
# 🔐 Azure IAM Lab – Role-Based Access & Least Privilege

Welcome to the **Azure IAM Lab**, where we go beyond theory and actually enforce **least privilege** in a real cloud environment.

This lab is designed to show how access control, role assignments, and visibility work together in Azure to build a secure identity perimeter.

---

## 🎯 Lab Goals

- Practice **least privilege** by creating custom roles
- Apply **RBAC** at different scopes: resource, RG, and subscription
- Use **Azure AD Privileged Identity Management (PIM)** for just-in-time elevation (simulated manually)
- Track **who did what** using Activity Logs and Azure Monitor
- Show how "access control" is more than assigning Reader to everyone 🙃

---

## 🧱 Architecture Overview

- A protected resource (Key Vault or Storage Account)
- Azure AD users or groups
- Custom RBAC Role (read-only, scoped to 1 resource)
- Manually elevated Contributor role (simulating PIM, PIM not available due subscription and cost limitation)
- Azure Monitor + Activity Logs enabled for auditing

![Architecture Diagram](./architecture/iam-lab-diagram.drawio.png)

---

## 🛠️ Steps

### 1. Set up the environment

- Create a Resource Group
- Add a Key Vault or Storage Account
- Create test users in Azure AD

### 2. Create and Assign Roles

- Create a **custom role** scoped to one resource
- Assign it to a test user
- Use PIM to make another user an **eligible contributor**

### 3. Test Access

- Log in as the custom role user → try to view/modify the resource
- Log in as the PIM user → elevate access → verify privileges
- Try over-assigning and review what the user can/can’t do

### 4. Enable Logging

- Enable Diagnostic Settings on the resource
- Route logs to Log Analytics Workspace
- Create a basic **KQL query** for activity by user/resource

---

## ✅ Real Lab Findings

- **Custom role successfully limited user access** to a single Key Vault, enforcing read-only access to secrets.
- The **Contributor role was manually assigned** to simulate elevated access in place of PIM.
- After a short delay, **User2 could create, update, and delete secrets**, confirming scoped access worked.
- **Diagnostic settings and Log Analytics** were configured correctly.
- While some identity fields (like `Identity` and `CallerIpAddress`) were not present, the `Caller` field allowed access tracking.
- **KQL queries** confirmed operations like `SecretGet` and `SecretSet`.


---


## 💬 Share Your Results

Tag me or fork the repo — I’d love to see how you approach IAM in Azure!  


#Azure #IAM #LeastPrivilege #RBAC #PIM #CloudSecurity #Cybersecurity #AzureLabs #LearningInPublic
