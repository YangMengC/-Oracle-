# SQL 命令





>  @("at" sign)
>  ---------------------
>
>   Runs the SQL*Plus statements in the specified script. The script can be called from the local file system or a web server.
>
> 在指定的脚本中运行 SQL*Plus 语句。可以从本地文件系统或 Web 服务器调用该脚本。
>
>  @ {url|file_name[.ext]} [arg ...]
>
>  where url supports HTTP and FTP protocols in the form:
>
>     http://host.domain/script.sql

   

>  @@ (double "at" sign)
>  ---------------------
>
>  Runs the specified script. This command is almost identical to the @ command. It is useful for running nested scripts because it has the additional functionality of looking for the nested script in the same url or path as the calling script.
>
> 运行指定的脚本。此命令几乎与 @ 命令相同。它对于运行嵌套脚本非常有用，因为它具有在与调用脚本相同的 URL 或路径中查找嵌套脚本的附加功能。
>
>  @@ {url|file_name[.ext]} [arg ...]



> /           

  

>   ACCEPT
>  ------
>
>  Reads a line of input and stores it in a given substitution variable.
>
> 读取输入行并将其存储在给定的替换变量中。
>
>  ACC[EPT] variable [NUM[BER] | CHAR | DATE | BINARY_FLOAT | BINARY_DOUBLE]
>  [FOR[MAT] format] [DEF[AULT] default] [PROMPT text | NOPR[OMPT]] [HIDE]



> APPEND       



>  ARCHIVE LOG
>  -----------
>
>  Displays information about redo log files.
>
> 显示有关重做日志文件的信息。
>
>  ARCHIVE LOG LIST



>  ATTRIBUTE
>  ---------
>
>  Specifies display characteristics for a given attribute of an Object Type column, such as the format of NUMBER data. Columns and attributes should not have the same names as they share a common namespace. Lists the current display characteristics for a single attribute or all attributes.
>
> 指定"对象类型"列的给定属性的显示特征，如 NUMBER 数据的格式。列和属性不应具有相同的名称，因为它们共享一个公共命名空间。列出单个属性或所有属性的当前显示特征。
>
>  ATTRIBUTE [type_name.attribute_name [option ... ]]
>
>  where option represents one of the following terms or clauses:
>      ALI[AS] alias
>      CLE[AR]
>      FOR[MAT] format
>      LIKE {type_name.attribute_name | alias}
>      ON|OFF

 

>  BREAK
>  -----
>
>  Specifies where changes occur in a report and the formatting
>  action to perform, such as:
>
>  - suppressing display of duplicate values for a given column
>  - skipping a line each time a given column value changes
>  - printing computed figures each time a given column value
>    changes or at the end of the report.
>
>  Enter BREAK with no clauses to list the current BREAK definition.
>
> 指定报表中发生更改的位置和格式
>  要执行的操作，例如：
>
> - 禁止显示给定列的重复值
>  - 每次给定列值更改时跳过一行
>  - 每次打印给定列值时的计算数字
>    更改或在报告末尾。
>
>  输入不带子句的 BREAK 以列出当前 BREAK 定义。
>
>  BRE[AK] [ON report_element [action [action]]] ...
>
>  where report_element has the following syntax:
>      {column | expression | ROW | REPORT}
>
>  and where action has the following syntax:
>      [SKI[P] n | [SKI[P]] PAGE] [NODUP[LICATES] | DUP[LICATES]]    



>  BTITLE
>  ------
>
>  Places and formats a specified title at the bottom of each report page, or lists the current BTITLE definition.
>
> 将指定标题放置在每个报表页的底部并设置其格式，或列出当前 BTITLE 定义。
>
>  BTI[TLE] [printspec [text|variable] ...] | [OFF|ON]
>
>  where printspec represents one or more of the following clauses:
>
>      COL n          LE[FT]        BOLD
>      S[KIP] [n]     CE[NTER]      FORMAT text
>      TAB n          R[IGHT]    



>  CHANGE
>  ------
>
>  Changes the first occurrence of the specified text on the current line of the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands.
>
> 更改指定文本在 SQL 缓冲区的当前行上的第一个匹配项。缓冲区没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  C[HANGE] sepchar old [sepchar [new[sepchar]]

​      

>  CLEAR
>  -----
>
>  Resets or erases the current value or setting for the specified option.
>
> 重置或擦除指定选项的当前值或设置。
>
>  CL[EAR] option ...
>
>  where option represents one of the following clauses:
>      BRE[AKS]
>      BUFF[ER]
>      COL[UMNS]
>      COMP[UTES]
>      SCR[EEN]
>      SQL
>      TIMI[NG]

​       

>  COLUMN
>  ------
>
>  Specifies display attributes for a given column, such as:
>    - text for the column heading
>    - alignment for the column heading
>    - format for NUMBER data
>    -  wrapping of column data
>
> Also lists the current display attributes for a single column or all columns.
>
> 指定给定列的显示属性，例如：
>    - 列标题的文本
>    - 列标题的对齐方式
>    - 数字数据的格式
>    - 包装列数据
>
> 还列出了单个列或所有列的当前显示属性。
>
>  COL[UMN] [{column | expr} [option ...] ]
>
>  where option represents one of the following clauses:
>      ALI[AS] alias
>      CLE[AR]
>      ENTMAP {ON|OFF}
>      FOLD_A[FTER]
>      FOLD_B[EFORE]
>      FOR[MAT] format
>      HEA[DING] text
>      JUS[TIFY] {L[EFT] | C[ENTER] | R[IGHT]}
>      LIKE {expr | alias}
>      NEWL[INE]
>      NEW_V[ALUE] variable
>      NOPRI[NT] | PRI[NT]
>      NUL[L] text
>      OLD_V[ALUE] variable
>      ON|OFF
>      WRA[PPED] | WOR[D_WRAPPED] | TRU[NCATED 

​      

>  COMPUTE
>  -------
>
>  In combination with the BREAK command, calculates and prints summary lines using various standard computations. Also lists all COMPUTE definitions.
>
> 与 BREAK 命令结合使用时，使用各种标准计算来计算和打印摘要行。还列出了所有计算定义。
>
>  COMP[UTE] [function [LAB[EL] text] ...
>    OF {expr|column|alias} ...
>    ON {expr|column|alias|REPORT|ROW} ...]  

  

> CONNECT      



>  COPY
>  ----
>
>  Copies data from a query to a table in the same or another database. COPY supports CHAR, DATE, LONG, NUMBER and VARCHAR2.
>
> 将数据从查询复制到同一数据库或其他数据库中的表。COPY 支持 CHAR、DATE、LONG、NUMBER 和 VARCHAR2。
>
>  COPY {FROM database | TO database | FROM database TO database}
>             {APPEND|CREATE|INSERT|REPLACE} destination_table
>             [(column, column, column, ...)] USING query
>
>  where database has the following syntax:
>      username[/password]@connect_identifier

​      

>  DEFINE
>  ------
>
>  Specifies a substitution variable and assigns a CHAR value to it, or lists the value and variable type of a single variable or all variables.
>
> 指定替换变量并为其赋值，或列出单个变量或所有变量的值和变量类型。
>
>  DEF[INE] [variable] | [variable = text]      



>  DEL
>  ---
>
>  Deletes one or more lines of the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands.
>
> 删除 SQL 缓冲区的一行或多行。缓冲区没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  DEL [n | n m | n * | n LAST | * | * n | * LAST | LAST]     



>  DESCRIBE
>  --------
>
>  Lists the column definitions for a table, view, or synonym, or the specifications for a function or procedure.
>
> 列出表、视图或同义词的列定义，或者列出函数或过程的规范。
>
>  DESC[RIBE] {[schema.]object[@connect_identifier]}

​    

>  DISCONNECT
>  ----------
>
>  Commits pending changes to the database and logs the current user out of Oracle, but does not exit SQL*Plus. In SQL*Plus command line, use EXIT or QUIT to log out of Oracle and return control to your computer's operating system.
>
> 将挂起的更改提交到数据库，并将当前用户从 Oracle 中注销，但不退出 SQL*Plus。在 SQL*Plus 命令行中，使用 EXIT 或 QUIT 注销 Oracle 并将控制权返回到计算机的操作系统。
>
>  DISC[ONNECT]

 

>  EDIT
>  ----
>
>  Invokes an operating system text editor on the contents of the specified file or on the contents of the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands.
>
> 对指定文件的内容或 SQL 缓冲区的内容调用操作系统文本编辑器。缓冲区没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  ED[IT] [file_name[.ext]] 

   

>  EXECUTE
>  -------
>
>  Executes a single PL/SQL statement or runs a stored procedure.
>
> 执行单个 PL/SQL 语句或运行存储过程。
>
>  EXEC[UTE] statement 

   

>  EXIT
>  ----
>
>  Commits or rolls back all pending changes, logs out of Oracle, terminates SQL*Plus and returns control to the operating system.
>
> 提交或回滚所有挂起的更改，注销 Oracle，终止 SQL*Plus 并将控制权返回给操作系统。
>
>  {EXIT|QUIT} [SUCCESS|FAILURE|WARNING|n|variable|:BindVariable]
>    [COMMIT|ROLLBACK]        



>  GET
>  ---
>
>  Loads a SQL statement or PL/SQL block from a script into the SQL buffer.
>  The buffer has no command history list and does not record SQL*Plus commands.
>
> 将 SQL 语句或 PL/SQL 块从脚本加载到 SQL 缓冲区中。
>  缓冲区没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  GET [FILE] file_name[.ext] [LIST | NOLIST]       



>  HELP
>  ----
>
>  Accesses this command line help system. Enter HELP INDEX or ? INDEX for a list of topics.
>
> 访问此命令行帮助系统。输入帮助索引或 ？主题列表的索引。
>
>  You can view SQL*Plus resources at
>      http://www.oracle.com/technology/tech/sql_plus/
>  and the Oracle Database Library at
>      http://www.oracle.com/technology/documentation/
>
>  HELP|? [topic]    



>  HOST
>  ----
>
>  Executes an operating system command without leaving SQL*Plus.
>  Enter HOST without command to display an operating system prompt.
>  You can then enter multiple operating system commands.
>
> 在不离开 SQL*Plus 的情况下执行操作系统命令。
>  输入 HOST（无命令）以显示操作系统提示符。
>  然后，您可以输入多个操作系统命令。
>
>  HO[ST] [command]        



>  INPUT
>  -----
>
>  Adds one or more new lines of text after the current line in the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands.
>
> 在 SQL 缓冲区中的当前行之后添加一行或多行新文本。缓冲区没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  I[NPUT] [text]    



>  LIST
>  ----
>
>  Lists one or more lines of the most recently executed SQL command or PL/SQL block which is stored in the SQL buffer. Enter LIST with no clauses to list all lines. In SQ*Plus command-line you can also use ";" to list all the lines in the SQL buffer. The buffer has no command history list and does not record SQL*Plus commands.
>
> 列出存储在 SQL 缓冲区中的最近执行的 SQL 命令或 PL/SQL 块的一行或多行。输入不带子句的 LIST 以列出所有行。在 SQ*Plus 命令行中，您还可以使用 ";" 列出 SQL 缓冲区中的所有行。缓冲区没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  L[IST] [n | n m | n  * | n LAST | * | * n | * LAST | LAST]



>  PASSWORD
>  --------
>
>  Allows you to change a password without displaying it on an input device.
>
> 允许您更改密码，而不在输入设备上显示密码。
>
>  PASSW[ORD] [username] 



>  PAUSE
>  -----
>
>  Displays the specified text then waits for the user to press RETURN.
>
> 显示指定的文本，然后等待用户按 RETURN 键。
>
>  PAU[SE] [text]                  



>  PRINT
>  -----
>
>  Displays the current values of bind variables, or lists all bind variables.
>
> 显示绑定变量的当前值，或列出所有绑定变量。
>
>  PRINT [variable ...]                



>  PROMPT
>  ------
>
>  Sends the specified message or a blank line to the user's screen.
>
> 将指定的消息或空行发送到用户的屏幕。
>
>  PRO[MPT] [text]                 



>  QUIT (Identical to EXIT)
>  ----
>
>  Commits or rolls back all pending changes, logs out of Oracle, terminates SQL*Plus and returns control to the operating system.
>
> 提交或回滚所有挂起的更改，注销 Oracle，终止 SQL*Plus 并将控制权返回给操作系统。
>
>  {QUIT|EXIT} [SUCCESS|FAILURE|WARNING|n|variable|:BindVariable]
>    [COMMIT|ROLLBACK]                 



>  RECOVER
>  -------
>
>  Performs media recovery on one or more tablespaces, one or more datafiles, or the entire database.
>
> 对一个或多个表空间、一个或多个数据文件或整个数据库执行媒体恢复。
>
>  RECOVER {general | managed} | BEGIN BACKUP | END BACKUP}
>
>  where the general clause has the following syntax:
>    [AUTOMATIC] [FROM location]
>    { {full_database_recovery | partial_database_recovery |LOGFILE filename}
>    [ {TEST | ALLOW integer CORRUPTION | parallel_clause}
>    [TEST | ALLOW integer CORRUPTION | parallel_clause] ...]
>    |CONTINUE [DEFAULT]|CANCEL}
>
>    where the full_database_recovery clause has the following syntax:
>      [STANDBY] DATABASE
>      [{ UNTIL {CANCEL | TIME date | CHANGE integer}
>       | USING BACKUP CONTROLFILE}
>       [ UNTIL {CANCEL | TIME date | CHANGE integer}
>       | USING BACKUP CONTROLFILE] ...]
>
>    where the partial_database_recovery clause has the following syntax:
>      {TABLESPACE tablespace [, tablespace] ...
>       | DATAFILE filename | filenumber} [,filename | filenumber] ...
>       | STANDBY
>        {TABLESPACE tablespace [, tablespace] ...
>        | DATAFILE filename | filenumber} [,filename | filenumber] ...}
>      UNTIL [CONSISTENT WITH] CONTROLFILE }
>
>  where the parallel clause has the following syntax:
>    {NOPARALLEL | PARALLEL [integer]}
>
>  where the managed clause has the following syntax:
>    MANAGED STANDBY DATABASE recover_clause | cancel_clause | finish_clause
>
>  where the recover_clause has the following syntax:
>    {{DISCONNECT [FROM SESSION] | {TIMEOUT integer | NOTIMEOUT} }
>     |{NODELAY | DEFAULT DELAY | DELAY integer} | NEXT integer
>     |{EXPIRE integer | NO EXPIRE} | parallel_clause
>     | USING CURRENT LOGFILE | UNTIL CHANGE integer
>     | THROUGH {[THREAD integer] SEQUENCE integer
>               | ALL ARCHIVELOG  | {ALL | LAST | NEXT } SWITCHOVER} }
>       [DISCONNECT [FROM SESSION ]  | {TIMEOUT integer | NOTIMEOUT}
>        | {NODELAY | DEFAULT DELAY | DELAY integer} | NEXT integer
>        | {EXPIRE integer | NO EXPIRE} | parallel_clause
>        | USING CURRENT LOGFILE | UNTIL CHANGE integer
>        | THROUGH {[THREAD integer] SEQUENCE integer
>                  | ALL ARCHIVELOG  | {ALL | LAST | NEXT } SWITCHOVER} ]...
>
>  where the cancel_clause has the following syntax:
>    CANCEL [IMMEDIATE] [WAIT | NOWAIT]
>
>  where the finish_clause has the following syntax:
>    [DISCONNECT [FROM SESSION]] [parallel_clause]
>    FINISH [SKIP [STANDBY LOGFILE]] [WAIT | NOWAIT]
>
>  where the parallel_clause has the following syntax:
>    {NOPARALLEL | PARALLEL [integer] }                 



>  REMARK
>  ------
>
>  Begins a comment in a script. SQL*Plus does not interpret the comment as a command.
>
> 在脚本中开始注释。SQL*Plus 不会将注释解释为命令。
>
>  REM[ARK]                



>  REPFOOTER
>  ---------
>
>  Places and formats a footer at the bottom of a report, or lists the
>  REPFOOTER definition.
>
> 将页脚置入报表底部并设置其格式，或列出
>  改写者定义。
>
>  REPF[OOTER] [PAGE] [printspec [text|variable] ...] | [OFF|ON]
>
>  where printspec represents one or more of the following clauses:
>      COL n          LE[FT]        BOLD
>      S[KIP] [n]     CE[NTER]      FORMAT text
>      TAB n          R[IGHT]            



>  REPHEADER
>  ---------
>
>  Places and formats a header at the top of a report, or lists the REPHEADER definition.
>
> 将页眉置于报表顶部并设置其格式，或列出 REPHEADER 定义。
>
>  REPH[EADER] [PAGE] [printspec [text|variable] ...] | [OFF|ON]
>
>  where printspec represents one or more of the following clauses:
>      COL n          LE[FT]        BOLD
>      S[KIP] [n]     CE[NTER]      FORMAT text
>      TAB n          R[IGHT]              



>  RESERVED WORDS (SQL)
>  --------------------
>
>  SQL Reserved Words have special meaning in SQL, and may not be used for
>  identifier names unless enclosed in "quotes".
>
>  An asterisk (*) indicates words are also ANSI Reserved Words.
>
>  Oracle prefixes implicitly generated schema object and subobject names
>  with "SYS_". To avoid name resolution conflict, Oracle discourages you
>  from prefixing your schema object and subobject names with "SYS_".
>
> SQL 保留字在 SQL 中具有特殊含义，除非用"引号"括起来，否则不得用于标识符名称。
>
> 星号 （*） 表示单词也是 ANSI 保留字。
>
> Oracle 在隐式生成的架构对象和子对象名称前面加上"SYS_"前缀。为避免名称解析冲突，Oracle 不鼓励您在架构对象和子对象名称前面加上"SYS_"前缀。
>
> 
>
>  ACCESS          DEFAULT*         INTEGER*        ONLINE          START
>  ADD*            DELETE*          INTERSECT*      OPTION*         SUCCESSFUL
>  ALL*            DESC*            INTO*           OR*             SYNONYM
>  ALTER*          DISTINCT*        IS*             ORDER*          SYSDATE
>  AND*            DROP*            LEVEL*          PCTFREE         TABLE*
>  ANY*            ELSE*            LIKE*           PRIOR*          THEN*
>  AS*             EXCLUSIVE        LOCK            PRIVILEGES*     TO*
>  ASC*            EXISTS           LONG            PUBLIC*         TRIGGER
>  AUDIT           FILE             MAXEXTENTS      RAW             UID
>  BETWEEN*        FLOAT*           MINUS           RENAME          UNION*
>  BY*             FOR*             MLSLABEL        RESOURCE        UNIQUE*
>  CHAR*           FROM*            MODE            REVOKE*         UPDATE*
>  CHECK*          GRANT*           MODIFY          ROW             USER*
>  CLUSTER         GROUP*           NOAUDIT         ROWID           VALIDATE
>  COLUMN          HAVING*          NOCOMPRESS      ROWNUM          VALUES*
>  COMMENT         IDENTIFIED       NOT*            ROWS*           VARCHAR*
>  COMPRESS        IMMEDIATE*       NOWAIT          SELECT*         VARCHAR2
>  CONNECT*        IN*              NULL*           SESSION*        VIEW*
>  CREATE*         INCREMENT        NUMBER          SET*            WHENEVER*
>  CURRENT*        INDEX            OF*             SHARE           WHERE
>  DATE*           INITIAL          OFFLINE         SIZE*           WITH*
>  DECIMAL*        INSERT*          ON*             SMALLINT*



>  RESERVED WORDS (PL/SQL)
>  -----------------------
>
>  PL/SQL Reserved Words have special meaning in PL/SQL, and may not be used for identifier names (unless enclosed in "quotes").
>
> PL/SQL 保留字在 PL/SQL 中具有特殊含义，不得使用用于标识符名称（除非用"引号"括起来）。
>
>  An asterisk (*) indicates words are also SQL Reserved Words.
>
>  ALL*            DESC*           JAVA            PACKAGE         SUBTYPE
>  ALTER*          DISTINCT*       LEVEL*          PARTITION       SUCCESSFUL*
>  AND*            DO              LIKE*           PCTFREE*        SUM
>  ANY*            DROP*           LIMITED         PLS_INTEGER     SYNONYM*
>  ARRAY           ELSE*           LOCK*           POSITIVE        SYSDATE*
>  AS*             ELSIF           LONG*           POSITIVEN       TABLE*
>  ASC*            END             LOOP            PRAGMA          THEN*
>  AT              EXCEPTION       MAX             PRIOR*          TIME
>  AUTHID          EXCLUSIVE*      MIN             PRIVATE         TIMESTAMP
>  AVG             EXECUTE         MINUS*          PROCEDURE       TIMEZONE_ABBR
>  BEGIN           EXISTS*         MINUTE          PUBLIC*         TIMEZONE_HOUR
>  BETWEEN*        EXIT            MLSLABEL*       RAISE           TIMEZONE_MINUTE
>  BINARY_INTEGER  EXTENDS         MOD             RANGE           TIMEZONE_REGION
>  BODY            EXTRACT         MODE*           RAW*            TO*
>  BOOLEAN         FALSE           MONTH           REAL            TRIGGER*
>  BULK            FETCH           NATURAL         RECORD          TRUE
>  BY*             FLOAT*          NATURALN        REF             TYPE
>  CHAR*           FOR*            NEW             RELEASE         UI
>  CHAR_BASE       FORALL          NEXTVAL         RETURN          UNION*
>  CHECK*          FROM*           NOCOPY          REVERSE         UNIQUE*
>  CLOSE           FUNCTION        NOT*            ROLLBACK        UPDATE*
>  CLUSTER*        GOTO            NOWAIT*         ROW*            USE
>  COALESCE        GROUP*          NULL*           ROWID*          USER*
>  COLLECT         HAVING*         NULLIF          ROWNUM*         VALIDATE*
>  COMMENT*        HEAP            NUMBER*         ROWTYPE         VALUES*
>  COMMIT          HOUR            NUMBER_BASE     SAVEPOINT       VARCHAR*
>  COMPRESS*       IF              OCIROWID        SECOND          VARCHAR2*
>  CONNECT*        IMMEDIATE*      OF*             SELECT*         VARIANCE
>  CONSTANT        IN*             ON*             SEPERATE        VIEW*
>  CREATE*         INDEX*          OPAQUE          SET*            WHEN
>  CURRENT*        INDICATOR       OPEN            SHARE*          WHENEVER*
>  CURRVAL         INSERT*         OPERATOR        SMALLINT*       WHERE*
>  CURSOR          INTEGER*        OPTION*         SPACE           WHILE
>  DATE*           INTERFACE       OR*             SQL             WITH*
>  DAY             INTERSECT*      ORDER*          SQLCODE         WORK
>  DECIMAL*        INTERVAL        ORGANIZATION    SQLERRM         WRITE
>  DECLARE         INTO*           OTHERS          START*          YEAR
>  DEFAULT*        IS*             OUT             STDDEV          ZONE
>  DELETE*         ISOLATION



>  RUN
>  ---
>
>  Lists and executes the most recently executed SQL command or
>  PL/SQL block which is stored in the SQL buffer. The buffer has
>  no command history list and does not record SQL*Plus commands.
>
> 列出并执行最近执行的 SQL 命令，或者存储在 SQL 缓冲区中的 PL/SQL 块。缓冲区具有没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  R[UN]                     



>  SAVE
>  ----
>
>  Saves the contents of the SQL buffer in a script. The buffer has no command history list and does not record SQL*Plus commands.
>
> 将 SQL 缓冲区的内容保存在脚本中。这缓冲区没有命令历史记录列表，并且不记录 SQL*Plus 命令。
>
>  SAV[E] [FILE] file_name[.ext] [CRE[ATE] | REP[LACE] | APP[END]]                 



>  SET
>  ---
>
>  Sets a system variable to alter the SQL*Plus environment settings
>  for your current session. For example, to:
>    -   set the display width for data
>    -   customize HTML formatting
>    -   enable or disable printing of column headings
>    -   set the number of lines per page
>
> 设置系统变量以更改 SQL*Plus 环境设置
>  对于您当前的会话。例如，要：
>    - 设置数据的显示宽度
>    -  自定义HTML格式
>    - 启用或禁用列标题的打印
>    - 设置每页的行数
>
>  SET system_variable value
>
>  where system_variable and value represent one of the following clauses:
>
>    APPI[NFO]{OFF|ON|text}                   NEWP[AGE] {1|n|NONE}
>    ARRAY[SIZE] {15|n}                       NULL text
>    AUTO[COMMIT] {OFF|ON|IMM[EDIATE]|n}      NUMF[ORMAT] format
>    AUTOP[RINT] {OFF|ON}                     NUM[WIDTH] {10|n}
>    AUTORECOVERY {OFF|ON}                    PAGES[IZE] {14|n}
>    AUTOT[RACE] {OFF|ON|TRACE[ONLY]}         PAU[SE] {OFF|ON|text}
>      [EXP[LAIN]] [STAT[ISTICS]]             RECSEP {WR[APPED]|EA[CH]|OFF}
>    BLO[CKTERMINATOR] {.|c|ON|OFF}           RECSEPCHAR {_|c}
>    CMDS[EP] {;|c|OFF|ON}                    SERVEROUT[PUT] {ON|OFF}
>    COLSEP {_|text}                            [SIZE {n | UNLIMITED}]
>    CON[CAT] {.|c|ON|OFF}                      [FOR[MAT]  {WRA[PPED] |
>    COPYC[OMMIT] {0|n}                          WOR[D_WRAPPED] |
>    COPYTYPECHECK {ON|OFF}                      TRU[NCATED]}]
>    DEF[INE] {&|c|ON|OFF}                    SHIFT[INOUT] {VIS[IBLE] |
>    DESCRIBE [DEPTH {1|n|ALL}]                 INV[ISIBLE]}
>      [LINENUM {OFF|ON}] [INDENT {OFF|ON}]   SHOW[MODE] {OFF|ON}
>    ECHO {OFF|ON}                            SQLBL[ANKLINES] {OFF|ON}
>    EDITF[ILE] file_name[.ext]               SQLC[ASE] {MIX[ED] |
>    EMB[EDDED] {OFF|ON}                        LO[WER] | UP[PER]}
>    ERRORL[OGGING] {ON|OFF}                  SQLCO[NTINUE] {> | text}
>      [TABLE [schema.]tablename]             SQLN[UMBER] {ON|OFF}
>      [TRUNCATE] [IDENTIFIER identifier]     SQLPLUSCOMPAT[IBILITY] {x.y[.z]}
>    ESC[APE] {\|c|OFF|ON}                    SQLPRE[FIX] {#|c}
>    ESCCHAR {@|?|%|$|OFF}                    SQLP[ROMPT] {SQL>|text}
>    EXITC[OMMIT] {ON|OFF}                    SQLT[ERMINATOR] {;|c|ON|OFF}
>    FEED[BACK] {6|n|ON|OFF}                  SUF[FIX] {SQL|text}
>    FLAGGER {OFF|ENTRY|INTERMED[IATE]|FULL}  TAB {ON|OFF}
>    FLU[SH] {ON|OFF}                         TERM[OUT] {ON|OFF}
>    HEA[DING] {ON|OFF}                       TI[ME] {OFF|ON}
>    HEADS[EP] {||c|ON|OFF}                   TIMI[NG] {OFF|ON}
>    INSTANCE [instance_path|LOCAL]           TRIM[OUT] {ON|OFF}
>    LIN[ESIZE] {80|n}                        TRIMS[POOL] {OFF|ON}
>    LOBOF[FSET] {1|n}                        UND[ERLINE] {-|c|ON|OFF}
>    LOGSOURCE [pathname]                     VER[IFY] {ON|OFF}
>    LONG {80|n}                              WRA[P] {ON|OFF}
>    LONGC[HUNKSIZE] {80|n}                   XQUERY {BASEURI text|
>    MARK[UP] HTML [OFF|ON]                     ORDERING{UNORDERED|
>      [HEAD text] [BODY text] [TABLE text]              ORDERED|DEFAULT}|
>      [ENTMAP {ON|OFF}]                        NODE{BYVALUE|BYREFERENCE|
>      [SPOOL {OFF|ON}]                              DEFAULT}|
>      [PRE[FORMAT] {OFF|ON}]                   CONTEXT text}                    



>  SHOW
>  ----
>
>  Shows the value of a SQL*Plus system variable, or the current
>  SQL*Plus environment. SHOW SGA requires a DBA privileged login.
>
> 显示 SQL*Plus 系统变量的值或当前变量的值
>  SQL*Plus 环境。SHOW SGA 需要 DBA 特权登录。
>
>  SHO[W] option
>
>  where option represents one of the following terms or clauses:
>      system_variable
>      ALL
>      BTI[TLE]
>      ERR[ORS] [{FUNCTION | PROCEDURE | PACKAGE | PACKAGE BODY | TRIGGER
>         | VIEW | TYPE | TYPE BODY | DIMENSION | JAVA CLASS} [schema.]name]
>      LNO
>      PARAMETERS [parameter_name]
>      PNO
>      RECYC[LEBIN] [original_name]
>      REL[EASE]
>      REPF[OOTER]
>      REPH[EADER]
>      SGA
>      SPOO[L]
>      SPPARAMETERS [parameter_name]
>      SQLCODE
>      TT[ITLE]
>      USER



>  SHUTDOWN
>  --------
>
>  Shuts down a currently running Oracle Database instance, optionally
>  closing and dismounting a database.
>
> 关闭当前正在运行的 Oracle 数据库实例（可选）
>  关闭和卸除数据库。
>
>  SHUTDOWN [ABORT|IMMEDIATE|NORMAL|TRANSACTIONAL [LOCAL]]



>  SPOOL
>  -----
>
>  Stores query results in a file, or optionally sends the file to a printer.
>
> 将查询结果存储在文件中，或选择性地将文件发送到打印机。
>
>  SPO[OL] [file_name[.ext] [CRE[ATE] | REP[LACE] | APP[END]] | OFF | OUT]



>  SQLPLUS
>  -------
>
>  Starts SQL*Plus from the operating system prompt.
>
> 从操作系统提示符启动 SQL*Plus。
>
>  SQLPLUS [ [option] [logon|/NOLOG] [start] ]
>
>  where option has the following syntax:
>      -H[ELP]
>      | -V[ERSION]
>      | [[-C[OMPATIBILITY] x.y[.z]] [-L[OGON]]
>         [-M[ARKUP] markup_option] [-R[ESTRICT] {1|2|3}] [-S[ILENT]]]
>
>  and where markup_option has the following syntax:
>      HTML [ON|OFF] [HEAD text] [BODY text] [TABLE text]
>           [ENTMAP {ON|OFF}] [SPOOL {ON|OFF}] [PRE[FORMAT] {ON|OFF}]
>
>  and where logon has the following syntax:
>      {username[/password][@connect_identifier] | /}
>      [AS {SYSOPER|SYSDBA|SYSASM}] [edition=value]
>
>  and where start has the following syntax:
>      @{url|filename[.ext]} [arg ...]



>  START
>  -----
>
>  Runs the SQL*Plus statements in the specified script. The script can be
>  called from the local file system or a web server.
>
> 在指定的脚本中运行 SQL*Plus 语句。脚本可以是
>  从本地文件系统或 Web 服务器调用。
>
>  STA[RT] {url|file_name[.ext]} [arg ...]
>
>  where url supports HTTP and FTP protocols in the form:
>
>     http://host.domain/script.sql



>  STARTUP
>  -------
>
>  Starts an Oracle instance with several options, including mounting,
>  and opening a database.
>
> 使用多个选项启动 Oracle 实例，包括挂载、
>  并打开数据库。
>
>  STARTUP options | upgrade_options
>
>  where options has the following syntax:
>     [FORCE] [RESTRICT] [PFILE=filename] [QUIET] [ MOUNT [dbname] |
>     [ OPEN [open_options] [dbname] ] |
>     NOMOUNT ]
>
>  where open_options has the following syntax:
>     READ {ONLY | WRITE [RECOVER]} | RECOVER
>
>  and where upgrade_options has the following syntax:
>     [PFILE=filename] {UPGRADE | DOWNGRADE} [QUIET]



>  STORE
>  -----
>
>  Saves attributes of the current SQL*Plus environment in a script.
>
> 将当前 SQL*Plus 环境的属性保存在脚本中。
>
>  STORE {SET} file_name[.ext] [CRE[ATE] | REP[LACE] | APP[END]



>  TIMING
>  ------
>
>  Records timing data for an elapsed time period, lists the current
>  timer's name and timing data, or lists the number of active timers.
>
> 记录经过的时间段的计时数据，列出当前
>  计时器的名称和计时数据，或列出活动计时器的数量。
>
>  TIMI[NG] [START text|SHOW|STOP]



>  TTITLE
>  ------
>
>  Places and formats a title at the top of each report page.
>  Enter TTITLE with no clause to list its current definition.
>
>  The old form of TTITLE is used if only a single word or
>  a string in quotes follows the TTITLE command.
>
> 将标题放置在每个报表页的顶部并设置其格式。
>  输入不带子句的 TTITLE 以列出其当前定义。
>
> TTITLE的旧形式如果只有一个单词或
>  引号中的字符串跟在 TTITLE 命令后面。
>
>  TTI[TLE] [printspec [text|variable] ...] | [OFF|ON]
>
>  where printspec represents one or more of the following clauses:
>
>      COL n          LE[FT]        BOLD
>      S[KIP] [n]     CE[NTER]      FORMAT text
>      TAB n          R[IGHT]



>  UNDEFINE
>  --------
>
>  Deletes one or more substitution variables that you defined either
>  explicitly (with the DEFINE command), or implicitly (with a START
>  command argument).
>
> 删除您定义的一个或多个替换变量
>  显式（使用 DEFINE 命令）或隐式（使用 START）
>  命令参数）。
>
>  UNDEF[INE] variable ...



>  VARIABLE
>  --------
>
>  Declares a bind variable that can be referenced in PL/SQL, or
>  lists the current display characteristics for a single variable
>  or all variables.
>
> 声明可在 PL/SQL 中引用的绑定变量，或者
>  列出单个变量的当前显示特征
>  或所有变量。
>
> VAR[IABLE] [variable [type]]
>
>  where type represents one of the following:
>
>      NUMBER         CHAR          CHAR (n [CHAR|BYTE])
>      NCHAR          NCHAR (n)     VARCHAR2 (n [CHAR|BYTE])
>      NVARCHAR2 (n)  CLOB          NCLOB
>      REFCURSOR      BINARY_FLOAT  BINARY_DOUBLE



>  WHENEVER OSERROR
>  ----------------
>
>  Performs the specified action (exits SQL*Plus by default) if an
>  operating system error occurs (such as a file writing error).
>
> 执行指定的操作（默认情况下退出 SQL*Plus），如果
>  发生操作系统错误（如文件写入错误）。
>
>  WHENEVER OSERROR {EXIT [SUCCESS|FAILURE|n|variable|:BindVariable]
>                    [COMMIT|ROLLBACK] | CONTINUE [COMMIT|ROLLBACK|NONE]}



>  WHENEVER SQLERROR
>  -----------------
>
>  Performs the specified action (exits SQL*Plus by default) if a
>  SQL command or PL/SQL block generates an error.
>
> 执行指定的操作（默认情况下退出 SQL*Plus），如果
>  SQL 命令或 PL/SQL 块生成错误。
>
>  WHENEVER SQLERROR {EXIT [SUCCESS|FAILURE|WARNING|n|variable|:BindVariable]
>                     [COMMIT|ROLLBACK] | CONTINUE [COMMIT|ROLLBACK|NONE]}



>  XQUERY
>  ------
>
>  Performs an XQuery 1.0 query on a specified database. Attempting to use
>  XQUERY on a database earlier than Oracle Database 10g (Release 2) generates
>  an error.
>
> 对指定的数据库执行 XQuery 1.0 查询。尝试使用
>  在 Oracle Database 10g（第 2 版）生成的数据库上生成的数据库上的 XQUERY
>  错误。
>
>  XQUERY xquery_statement

