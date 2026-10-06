# Oracle PDB Assignment II

**Student Name:** Rutagengwa  
**Student ID:** 28468  
**Repository:** oracle_pdb_ass_II_28468_rutagengwa

---

## 1. Overview of Tasks

This repository contains the evidence and documentation for Assignment II on Oracle Pluggable Databases (PDBs).

The four mandatory tasks completed are:

1. Create a permanent Pluggable Database and a dedicated user
2. Create and completely delete a temporary Pluggable Database
3. Access Oracle Enterprise Manager (EM Express) and capture the dashboard
4. Document the work and publish it on a public GitHub repository

---

## 2. Oracle Environment Used

- **Database Version:** Oracle Database 21c Express Edition (21.3.0.0.0)
- **Operating System:** Microsoft Windows 10/11 (64-bit)
- **Installation Path:** `C:\app\Envy\product\21c\`
- **Container Database (CDB):** XE
- **Tools Used:** SQL*Plus, Oracle Enterprise Manager Database Express (EM Express)

---

## 3. Explanation of Each Task

### Task 1 – Create a New Pluggable Database

- **PDB Name:** `ru_pdb_28468`
- **Admin User (during creation):** `pdbadmin`
- **Class User created inside the PDB:** `RUTAGENGWA_PLSQLAUCA_28468`
- The PDB was created successfully, opened in READ WRITE mode, and the required user was created and verified.

**Screenshots:**  
`screenshots/task1/`

### Task 2 – Create and Delete a Temporary PDB

- **Temporary PDB Name:** `ru_to_delete_pdb_28468`
- The PDB was created, opened, verified, closed, and then completely dropped using `INCLUDING DATAFILES`.
- Final verification confirmed that the temporary PDB no longer exists.

**Screenshots:**  
`screenshots/task2/`

### Task 3 – Oracle Enterprise Manager (OEM)

- EM Express was successfully accessed at `https://localhost:5500/em`
- The dashboard shows the Oracle environment (XE 21.3, Windows, CDB with PDBs)
- The permanent PDB `RU_PDB_28468` is visible in the environment

**Screenshot:**  
`screenshots/task3/oem_dashboard.png`

---

## 4. Challenges Faced and Solutions

| Challenge | Solution |
|---------|----------|
| Listener was configured with an old IP address (`192.168.1.26`) and would not start | Edited `listener.ora` and changed `HOST` to `localhost` |
| Database was not registering with the listener | Set `LOCAL_LISTENER` parameter and executed `ALTER SYSTEM REGISTER` |
| EM Express (port 5500) was not accessible | After successful registration of the XE and XEXDB services, `DBMS_XDB_CONFIG.SETHTTPSPORT(5500)` was executed |
| Temporary PDB could not be dropped from inside a PDB | Switched to `CDB$ROOT` before issuing the `DROP` command |

---

## 5. Integrity Statement

I hereby declare that all the work submitted in this repository is my own. All screenshots and commands were executed by me on my local Oracle 21c XE environment. I did not copy or submit anyone else’s work.

---

## 6. Submission Details

- **Repository Link:** https://github.com/[your-username]/oracle_pdb_ass_II_28468_rutagengwa
- **PDB Name Created:** `ru_pdb_28468`
- **Temporary PDB Name:** `ru_to_delete_pdb_28468`
- **Class User:** `RUTAGENGWA_PLSQLAUCA_28468`
- **Issues Encountered:** Yes (Listener registration and EM Express access – successfully resolved)

---

**End of Report**
