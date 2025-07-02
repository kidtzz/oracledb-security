# Database Security Workshop: Database Vault

# Getting Started

***To log issues***, click here to go to the [github oracle](https://github.com/kwazulu/dbsec-workshop/issues/new) repository issue submission form.


## LAB 300 - DATABASE VAULT OPERATIONS CONTROL

In this lab, you will use Oracle Database 19c and the Oracle Database Vault 19c new feature of Operations Control. Ops Control, for short, allows users to keep container-level administrators (users prefixed with C##) out of pluggable database data. The container administrators can access the pluggable database but cannot query application data. 

- Open a Terminal and start SQL*Plus without logging in as any user

    ```bash 
    sqlplus /nolog
    ```

- Demonstrate that Zeus can connect to the CDB and the PDB databases

    ```bash
    connect c##zeus/Oracle123
    show user;
    show con_name

    connect c##zeus/Oracle123@pdb1
    show user;
    show con_name
    ```
    
- Demonstrate Zeus can query the sensitive employee table

    ```bash 
    select count(*) from employeesearch.demo_hr_employees; 
    ```

- Enable Database Vault Operations Control

    ```bash 
    connect c##dbv_owner/Oracle123
    EXEC DBMS_MACADM.ENABLE_APP_PROTECTION;
    connect sys/Oracle123 as sysdba
    set lines 140
    column name format a25
    column status format a20
    select * From dba_dv_status;
    ```
    
- Demonstrate that Zeus can connect to the CDB and the PDB

    ```bash 
    connect c##zeus/Oracle123
    show user;
    show con_name
    
    connect c##zeus/Oracle123@pdb1
    show user;
    show con_name
    ```

- Demonstrate Zeus can no longer query the sensitive employee table

    ```bash 
    select count(*) from employeesearch.demo_hr_employees;
    ```

- Disable Database Vault Operations Control

    ```bash 
    connect c##dbv_owner/Oracle123
    EXEC DBMS_MACADM.DISABLE_APP_PROTECTION;
    connect sys/Oracle123 as sysdba
    set lines 140
    column name format a25
    column status format a20
    select * From dba_dv_status;
    ```
    
- Demonstrate that Zeus can connect to the CDB and the PDB

    ```bash 
    connect c##zeus/Oracle123
    show user;
    show con_name
    
    connect c##zeus/Oracle123@pdb1
    show user;
    show con_name
    ```bash 
    
- Demonstrate Zeus can query the sensitive employee table

    ```bash 
    select count(*) from employeesearch.demo_hr_employees;
    ```

 #### Conclusion

In this lab, you used Database Vault 19c Ops Control to protect application data in pluggable databases from container-level administrators.

**This completes this Lab!**

--- 

[Database Vault Landing Page](../README.md)

[Database Security Workshop Landing Page](https://github.com/kwazulu/dbsec-workshop/blob/master/README.md)