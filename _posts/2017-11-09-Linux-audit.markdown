```go
 	GET         1000 /* Get status */
 	SET         1001 /* Set status (enable/disable/auditd) */
 	LIST        1002 /* List syscall rules -- deprecated */
 	ADD         1003 /* Add syscall rule -- deprecated */
 	DEL         1004 /* Delete syscall rule -- deprecated */
 	USER        1005 /* Message from userspace -- deprecated */
 	LOGIN       1006 /* Define the login id and information */
 	WATCH_INS   1007 /* Insert file/dir watch entry */
 	WATCH_REM   1008 /* Remove file/dir watch entry */
 	WATCH_LIST  1009 /* List all file/dir watches */
 	SIGNAL_INFO 1010 /* Get info about sender of signal to auditd */
 	ADD_RULE    1011 /* Add syscall filtering rule */
 	DEL_RULE    1012 /* Delete syscall filtering rule */
 	LIST_RULES  1013 /* List syscall filtering rules */
 	TRIM        1014 /* Trim junk from watched tree */
    MAKE_EQUIV  1015 /* Append to watched tree */
    TTY_GET     1016 /* Get TTY auditing status */
    TTY_SET     1017 /* Set TTY auditing status */
    SET_FEATURE 1018 /* Turn an audit feature on or off */
    GET_FEATURE 1019 /* Get which features are enabled */

    FIRST_USER_MSG   1100 /* First user space message */
    LAST_USER_MSG    1199 /* Last user space message */
    USER_AUTH        1100 /* User space authentication */
    USER_ACCT        1101 /* User space acct change */
    USER_MGMT        1102 /* User space acct management */
    CRED_ACQ         1103 /* User space credential acquired */
    CRED_DISP        1104 /* User space credential disposed */
    USER_START       1105 /* User space session start */
    USER_END         1106 /* User space session end */
    USER_AVC         1107 /* User space avc message */
    USER_CHAUTHTOK   1108 /* User space acct attr changed */
    USER_ERR         1109 /* User space acct state err */
    CRED_REFR        1110 /* User space credential refreshed */
    USYS_CONFIG      1111 /* User space system config change */
    USER_LOGIN       1112 /* User space user has logged in */
    USER_LOGOUT      1113 /* User space user has logged out */
    ADD_USER         1114 /* User space user account added */
    DEL_USER         1115 /* User space user account deleted */
    ADD_GROUP        1116 /* User space group added */
    DEL_GROUP        1117 /* User space group deleted */
    DAC_CHECK        1118 /* User space DAC check results */
    CHGRP_ID         1119 /* User space group ID changed */
    TEST             1120 /* Used for test success messages */
    TRUSTED_APP      1121 /* Trusted app msg - freestyle text */
    USER_SELINUX_ERR 1122 /* SE Linux user space error */
    USER_CMD         1123 /* User shell command and args */
    USER_TTY         1124 /* Non-ICANON TTY input meaning */
    CHUSER_ID        1125 /* Changed user ID supplemental data */
    GRP_AUTH         1126 /* Authentication for group password */
    SYSTEM_BOOT      1127 /* System boot */
    SYSTEM_SHUTDOWN  1128 /* System shutdown */
    SYSTEM_RUNLEVEL  1129 /* System runlevel change */
    SERVICE_START    1130 /* Service (daemon) start */
    SERVICE_STOP     1131 /* Service (daemon) stop */
    GRP_MGMT         1132 /* Group account attr was modified */
    GRP_CHAUTHTOK    1133 /* Group acct password or pin changed */
    MAC_CHECK        1134 /* User space MAC decision results */
    ACCT_LOCK        1135 /* User's account locked by admin */
    ACCT_UNLOCK      1136 /* User's account unlocked by admin */

    FIRST_DAEMON    1200
    LAST_DAEMON     1299
    DAEMON_CONFIG   1203 /* Daemon config change */
    DAEMON_RECONFIG 1204 /* Auditd should reconfigure */
    DAEMON_ROTATE   1205 /* Auditd should rotate logs */
    DAEMON_RESUME   1206 /* Auditd should resume logging */
    DAEMON_ACCEPT   1207 /* Auditd accepted remote connection */
    DAEMON_CLOSE    1208 /* Auditd closed remote connection */

    SYSCALL 1300 /* Syscall event */
    /* FS_WATCH     auditConstant       =   1301     * Deprecated */
    PATH           1302 /* Filename path information */
    IPC            1303 /* IPC record */
    SOCKETCALL     1304 /* sys_socketcall arguments */
    CONFIG_CHANGE  1305 /* Audit system configuration change */
    SOCKADDR       1306 /* sockaddr copied as syscall arg */
    CWD            1307 /* Current working directory */
    EXECVE         1309 /* execve arguments */
    IPC_SET_PERM   1311 /* IPC new permissions record type */
    MQ_OPEN        1312 /* POSIX MQ open record type */
    MQ_SENDRECV    1313 /* POSIX MQ send/receive record type */
    MQ_NOTIFY      1314 /* POSIX MQ notify record type */
    MQ_GETSETATTR  1315 /* POSIX MQ get/set attribute record type */
    KERNEL_OTHER   1316 /* For use by 3rd party modules */
    FD_PAIR        1317 /* audit record for pipe/socketpair */
    OBJ_PID        1318 /* ptrace target */
    TTY            1319 /* Input on an administrative TTY */
    EOE            1320 /* End of multi-record event */
    BPRM_FCAPS     1321 /* Information about fcaps increasing perms */
    CAPSET         1322 /* Record showing argument to sys_capset */
    MMAP           1323 /* Record showing descriptor and flags in mmap */
    NETFILTER_PKT  1324 /* Packets traversing netfilter chains */
    NETFILTER_CFG  1325 /* Netfilter chain modifications */
    SECCOMP        1326 /* Secure Computing event */
    PROCTITLE      1327 /* Proctitle emit event */
    FEATURE_CHANGE 1328 /* audit log listing feature changes */

    /* FIRST_EVENT       1300 */ //TODO: libaudit define this as FIRST_EVENT but audit.h differently.
    LAST_EVENT                   1399

    /* FIRST_SELINUX     1400 */ // TODO: libaudit define this as FIRST_SELINUX but audit.h as AVC
    AVC                          1400 /* SE Linux avc denial or grant */
    SELINUX_ERR                  1401 /* internal SE Linux Errors */
    AVC_PATH                     1402 /* dentry, vfsmount pair from avc */
    MAC_POLICY_LOAD              1403 /* Policy file load */
    MAC_STATUS                   1404 /* Changed enforcing,permissive,off */
    MAC_CONFIG_CHANGE            1405 /* Changes to booleans */
    MAC_UNLBL_ALLOW              1406 /* NetLabel: allow unlabeled traffic */
    MAC_CIPSOV4_ADD              1407 /* NetLabel: add CIPSOv4 DOI entry */
    MAC_CIPSOV4_DEL              1408 /* NetLabel: del CIPSOv4 DOI entry */
    MAC_MAP_ADD                  1409 /* NetLabel: add LSM domain mapping */
    MAC_MAP_DEL                  1410 /* NetLabel: del LSM domain mapping */
    MAC_IPSEC_ADDSA              1411 /* Not used */
    MAC_IPSEC_DELSA              1412 /* Not used  */
    MAC_IPSEC_ADDSPD             1413 /* Not used */
    MAC_IPSEC_DELSPD             1414 /* Not used */
    MAC_IPSEC_EVENT              1415 /* Audit an IPSec event */
    MAC_UNLBL_STCADD             1416 /* NetLabel: add a static label */
    MAC_UNLBL_STCDEL             1417 /* NetLabel: del a static label */
    LAST_SELINUX                 1499

    FIRST_APPARMOR 1500
    LAST_APPARMOR  1599

    AA               1500 /* Not upstream yet*/
    APPARMOR_AUDIT   1501
    APPARMOR_ALLOWED 1502
    APPARMOR_DENIED  1503
    APPARMOR_HT      1504
    APPARMOR_STATUS  1505
    APPARMOR_ERROR   1506

    FIRST_KERN_CRYPTO_MSG 1600
    LAST_KERN_CRYPTO_MSG  1699

    // FIRST_KERN_ANOM_MSG 1700
    LAST_KERN_ANOM_MSG 1799
    ANOM_PROMISCUOUS   1700 /* Device changed promiscuous mode */
    ANOM_ABEND         1701 /* Process ended abnormally */
    ANOM_LINK          1702 /* Suspicious use of file links */

    INTEGRITY_FIRST_MSG 1800
    TINTEGRITY_LAST_MSG 1899

    INTEGRITY_DATA     1800 /* Data integrity verification */
    INTEGRITY_METADATA 1801 // Metadata integrity verification
    INTEGRITY_STATUS   1802 /* integrity enable status */
    INTEGRITY_HASH     1803 /* integrity HASH type */
    INTEGRITY_PCR      1804 /* PCR invalidation msgs */
    INTEGRITY_RULE     1805 /* Policy rule */
    KERNEL             2000 /* Asynchronous audit record. NOT A REQUEST. */

    FIRST_ANOM_MSG           2100
    LAST_ANOM_MSG            2199
    ANOM_LOGIN_FAILURES      2100 // Failed login limit reached
    ANOM_LOGIN_TIME          2101 // Login attempted at bad time
    ANOM_LOGIN_SESSIONS      2102 // Max concurrent sessions reached
    ANOM_LOGIN_ACCT          2103 // Login attempted to watched acct
    ANOM_LOGIN_LOCATION      2104 // Login from forbidden location
    ANOM_MAX_DAC             2105 // Max DAC failures reached
    ANOM_MAX_MAC             2106 // Max MAC failures reached
    ANOM_AMTU_FAIL           2107 // AMTU failure
    ANOM_RBAC_FAIL           2108 // RBAC self test failure
    ANOM_RBAC_INTEGRITY_FAIL 2109 // RBAC file Tegrity failure
    ANOM_CRYPTO_FAIL         2110 // Crypto system test failure
    ANOM_ACCESS_FS           2111 // Access of file or dir
    ANOM_EXEC                2112 // Execution of file
    ANOM_MK_EXEC             2113 // Make an executable
    ANOM_ADD_ACCT            2114 // Adding an acct
    ANOM_DEL_ACCT            2115 // Deleting an acct
    ANOM_MOD_ACCT            2116 // Changing an acct
    ANOM_ROOT_TRANS          2117 // User became root

    FIRST_ANOM_RESP        2200
    LAST_ANOM_RESP         2299
    RESP_ANOMALY           2200 /* Anomaly not reacted to */
    RESP_ALERT             2201 /* Alert email was sent */
    RESP_KILL_PROC         2202 /* Kill program */
    RESP_TERM_ACCESS       2203 /* Terminate session */
    RESP_ACCT_REMOTE       2204 /* Acct locked from remote access*/
    RESP_ACCT_LOCK_TIMED   2205 /* User acct locked for time */
    RESP_ACCT_UNLOCK_TIMED 2206 /* User acct unlocked from time */
    RESP_ACCT_LOCK         2207 /* User acct was locked */
    RESP_TERM_LOCK         2208 /* Terminal was locked */
    RESP_SEBOOL            2209 /* Set an SE Linux boolean */
    RESP_EXEC              2210 /* Execute a script */
    RESP_SINGLE            2211 /* Go to single user mode */
    RESP_HALT              2212 /* take the system down */

    FIRST_USER_LSPP_MSG    2300
    LAST_USER_LSPP_MSG     2399
    USER_ROLE_CHANGE       2300 /* User changed to a new role */
    ROLE_ASSIGN            2301 /* Admin assigned user to role */
    ROLE_REMOVE            2302 /* Admin removed user from role */
    LABEL_OVERRIDE         2303 /* Admin is overriding a label */
    LABEL_LEVEL_CHANGE     2304 /* Object's level was changed */
    USER_LABELED_EXPORT    2305 /* Object exported with label */
    USER_UNLABELED_EXPORT  2306 /* Object exported without label */
    DEV_ALLOC              2307 /* Device was allocated */
    DEV_DEALLOC            2308 /* Device was deallocated */
    FS_RELABEL             2309 /* Filesystem relabeled */
    USER_MAC_POLICY_LOAD   2310 /* Userspc daemon loaded policy */
    ROLE_MODIFY            2311 /* Admin modified a role */
    USER_MAC_CONFIG_CHANGE 2312 /* Change made to MAC policy */

    FIRST_CRYPTO_MSG         2400
    CRYPTO_TEST_USER         2400 /* Crypto test results */
    CRYPTO_PARAM_CHANGE_USER 2401 /* Crypto attribute change */
    CRYPTO_LOGIN             2402 /* Logged in as crypto officer */
    CRYPTO_LOGOUT            2403 /* Logged out from crypto */
    CRYPTO_KEY_USER          2404 /* Create,delete,negotiate */
    CRYPTO_FAILURE_USER      2405 /* Fail decrypt,encrypt,randomiz */
    CRYPTO_REPLAY_USER       2406 /* Crypto replay detected */
    CRYPTO_SESSION           2407 /* Record parameters set during TLS session establishment */
    CRYPTO_IKE_SA            2408 /* Record parameters related to IKE SA */
    CRYPTO_IPSEC_SA          2409 /* Record parameters related to IPSEC SA */

    LAST_CRYPTO_MSG 2499

    FIRST_VIRT_MSG  2500
    VIRT_CONTROL    2500 /* Start, Pause, Stop VM */
    VIRT_RESOURCE   2501 /* Resource assignment */
    VIRT_MACHINE_ID 2502 /* Binding of label to VM */
    LAST_VIRT_MSG   2599
    LAST_USER_MSG2  2999


```