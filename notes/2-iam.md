# OCI Identity and Access Management (IAM)

Oracle Cloud Infrastructure (OCI) uses **Identity and Access Management (IAM)** to control who can access resources and what actions they can perform. IAM is the foundation for secure and organized cloud operations.

---

## 1. Overview of IAM

IAM in OCI revolves around **identities** and **permissions**.  
Identities are entities that can access OCI resources, while permissions define what those identities are allowed to do.  

Key components include:

- **Principals**: These are IAM entities allowed to interact with OCI resources. Examples include IAM users, groups, and instance principals. Principals are essentially "actors" in the cloud environment.

- **IAM Users and Groups**:  
  - The first IAM user created in a tenancy is automatically the **default administrator**.  
  - Users are organized into groups. Policies are applied at the group level rather than for individual users.  
  - Each group should have at least one policy defining its access rights.

- **Instance Principals**:  
  - These allow **OCI compute instances** to make API calls against other OCI services without needing manual credentials.  
  - This enables automated, secure workflows where applications or services running on OCI can interact with other cloud resources.

- **Policies and Roles**:  
  - Roles such as Network Administrator or Storage Administrator are defined by policies.  
  - Policies specify **who can do what and where**, creating clear boundaries for resource management.

---

## 2. Authentication and Authorization

OCI IAM separates **authentication** from **authorization**:

- **Authentication** is about verifying identity.  
  - Users log in with **username and password**, **API signing keys**, or **auth tokens**.  
  - Authentication ensures that only valid users or services can access the OCI environment.

- **Authorization** defines **what actions the authenticated principal is allowed to perform**.  
  - Policies are the mechanism for authorization.  
  - Example: "Allow group NetworkAdmins to manage virtual-network-family in compartment Production."

---

## 3. Policies in OCI

Policies are statements that define access rules. They specify **who** can perform **which actions** on **what resources**, and optionally under **what conditions**.  

A typical policy follows this structure:  

**Allow <group> to <verb> <resource-type> in <compartment> where <conditions>**  

### Common Policy Verbs
- **Inspect**: List resources without accessing sensitive information.  
- **Read**: Inspect user-specified metadata or configuration.  
- **Use**: Includes read and update permissions, allowing modifications where applicable.  
- **Manage**: Grants full access, including create, update, and delete operations.

### Common Resource Types
- All resources: all-resources  
- Databases: database-family  
- Compute instances: instance-family  
- Storage: object-family  

### Examples of Common Policies
- Network Administrator: Manage all resources under virtual-network-family  
- Instance Launchers: Manage instance-family, use volume-family, and use virtual-network-family  

Policies provide **fine-grained control**, ensuring that teams have exactly the permissions they need without overexposing resources.

---

## 4. Best Practices

1. Always organize users into **groups** and assign policies at the group level.  
2. Use **instance principals** for automated scripts and applications instead of hardcoding credentials.  
3. Follow the **principle of least privilege** by granting only the permissions necessary for a role.  
4. Use meaningful **names for groups and policies** to make governance easier.  
5. Regularly review policies to ensure compliance and remove unnecessary permissions.

---

OCI IAM is a critical component of cloud security, providing a structured approach to access management, resource governance, and operational safety. Proper use of IAM ensures that cloud resources are **secure, auditable, and efficiently managed**.
