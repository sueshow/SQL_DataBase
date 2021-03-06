# DataBase



## 資料庫系統 (Database System)
* 資料庫系統分為三個部份：
  * 資料庫 (Database)
  * 資料庫管理系統 (DataBase Management System, DBMS)
  * 應用程式 (Application)
  * 補圖
* 資料庫系統的使用者
  * 資料庫設計者 (Database Designer)
  * 資料庫管理者 (DataBase Administrator, DBA)
  * 應用程式設計者 (Application Designer)
  * 一般使用者 (End user)
* 優點：
  * 能透過電腦化的資料儲存及管理, 減少人力及空間的浪費。
  * 能迅速、即時地提供使用者所需要的資料, 大幅降低公司的成本。
* 資料庫的類型
  * 階層式資料庫 (Hierarchical Database)
    * 採用樹狀的結構，將資料分門別類儲存在不同的階層下
    * 優點：資料結構類似金字塔，對於在同一類型中不同階層資料的描述非常簡單且清楚
    * 缺點：在於當資料的關係變得複雜時，會造成管理及維護的不便
    * 如 IBM 公司在 1968 年推出的第一個資料庫管理系統—IMS
  * 網狀式資料庫 (Network Database)
    * 是階層式資料庫的擴充，將每筆記錄想像成一個節點，節點與節點間可以建立關聯 (也就是建立記錄和記錄間的關聯)，形成一個複雜的網狀架構
    * 優點：避免階層式資料庫中資料重複的問題
    * 缺點：關聯比較複雜，尤其當資料庫的內容愈來愈多時，要維護之間的關聯性就會變得非常複雜
    * 如 1970 年代 Computer Associates 發展的 IDMS
  * 關聯式資料庫 (Relational Database)
    * 是以 2 維的矩陣來儲存資料 (將資料儲存在表格的欄、列之中)，而儲存在欄、列裡的資料必會有所「關聯」，儲存資料的表格則稱為「資料表」
    * 如 Microsoft SQL Server、SyBase、Informix、MySQL、PostgreSQL、Access...等
  * 物件導向式資料庫 (Object-Oriented Database)
    * 以物件導向的方式來設計資料庫，其中包含了物件的屬性、方法、類別、繼承等特性
    * 如 Computer Associates 公司的 Jasmine、Eastman Kodak 公司的 Alltalk、Servio 公司的 GemStone、O2 Technology 的 O2 ...等
    * 也有關聯式資料庫為主，再於其上架設物件導向概念的資料庫，如 PostgreSQL
* 處理架構
  * 單機架構
    * 利用一台電腦完成所有的工作，包含使用者存取資料、DBA 管理及維護資料庫...等
    * 適合在使用者少且資料量也不多的環境下使用
  * 大型主機 / 終端機架構
    * 由一台大型主機負責儲存及處理資料, 所有的用戶端僅供操作, 沒有處理資料的能力, 只能透過鍵盤及終端機傳送和顯示大型主機的訊息
    * 優點：主機完全掌控系統的資源, 所有管理及維護工作都只要針對主機即可, 環境較單純
    * 缺點：
      * 只有一台主機執行工作, 當連線的使用者增加時, 會因為處理的工作增加而降低執行的效率
      * 大型主機的價格昂貴
  * 主從式架構 (Client / Server)
    * 利用一台處理效能較強的電腦作為主機, 來維護資料庫及處理使用者提出的要求, 再利用使用者的個人電腦來分擔部分主機的工作 (例如提供操作介面及應用程式)
  * 分散式架構
    * 利用數台資料庫伺服器來分別處理使用者的連線
    * 使用者透過網路存取資料, 這些資料可能分別來自不同的主機, 如此分擔了一台主機的工作, 執行起來效能會更佳
<br>


## NoSQL (Not Only SQL)
* Key-Value資料庫
  * 特性：是NoSQL資料庫中最大宗的類型，具有水平擴充性、能依需求增加資料庫
  * 用途：用於儲存 TB 或 PB 等級資料
  * 產品：Google BigTable、Hadoop HBase、Amazon Dynamo、Cassandra、Hypertable
* 記憶體資料庫 (In-memory Database)
  * 特性：利用記憶體建立分散式資料庫，加快讀取資料的速度
  * 用途：用來快取常用網頁，減少讀取硬碟的次數，不過系統關機後就無法保存
  * 產品：Memcached、Redis
* 文件資料庫 (Document Database)
  * 特性：可儲存結構鬆散或非結構性的資料，很多文件資料庫是商本
  * 用途：用來儲存網頁資料或各種 XML 格式的文件，也可儲存圖片或影音資料
  * 產品：CouchDB、MongoDB、Riak
* 圖學資料庫 (Graph Database)
  * 特性：資料包括節點 (Node)、關係 (Relation)和屬性 (Property)三種結構，來儲存圖學架構
  * 用途：運用圖學架構來儲存節點間關係資料架構，例如用樹狀結構來組織從屬關係或網狀結構來儲存朋友關係，地理圖資系統通常也會用圖學資料庫來儲存地圖上每一點和鄰近點的關係，或用圖學資料庫來計算點與點之間最短的距離，也可以用同樣的概念來計算出人與人之間最短的交友距離
  * 產品：Neo4j、InfoGrid、AllegroGrph
<br>


## 資料庫正規化
* 目的：提高關聯性資料庫的效能
  * 降低資料重複性(Data Redundancy) (Data Redundancy)。
  * 避免資料更新異常(Anomalies)
* 將原先關聯 (表格) 的所有資訊，在「分解」之後，仍能由數個新關聯 (表格) 中經過「合併」得到相同的資訊。即所謂的「無損失分解
(Lossless decomposition)」的觀念
  * 符合第一條規則，資料庫就稱為「第一正規化形式 (1NF)」
    * 每一個欄位只能有一個基元值 (Atomic) 即單一值
    * 沒有任何兩筆以上的資料是完全重覆
    * 資料表中有主鍵，而其他所有的欄位都相依於「主鍵」
  * 符合前二條規則，資料庫就被視為屬於「第二正規化形式(2NF)」
    * 每一非鍵屬性 (如：姓名、性別…) 必須「完全相依」於主鍵(學號)；即不可「部分功能相依」於主鍵。換言之，「部分功能相依」只有當「主鍵」是由「多個欄位」組成時才會發生(亦即複合主鍵)，也就是當某些欄位只與「主鍵中的部分欄位」有「相依性」, 而與另一部分的欄位沒有相依性。
    * 不符合第 2 正規化，可能出現問題如下
      * 新增可能發生錯誤：如果僅增加一位學生『林秀氣』，當還未修讀任何課程，結果『課程名稱』欄位空白，違背主鍵不可 Null 之規定。
      * 更新可能發生錯誤：系上規定『資料庫管理系統』的學分數改為 4，如果僅更新『學號=40011223』的資料，其它同學的學分數就沒有變更到。
      * 刪除可能發生錯誤：如果刪除了學號=40011234 這筆資料，以後可能找不到『計算機概論』的資料了。
  * 符合前三條規則
    * 各欄位與「主鍵」之間沒有「遞移相依」的關係
    * 不符合第 3 正規化，可能出現問題如下
      * 更新可能出現錯誤：如果高雄市鳥松區的郵遞區號改為 850，如僅修改 40011223 這筆資料，則出現與 49921234 資料內郵遞區號不一致的現象。
      * 刪除可能出現錯誤：如刪除掉 40011234 這筆資料，可能無法再找到台南市安南區的郵遞區號資料了。
  * 雖然資料庫的正規化最多可以進行到第五正規化形式，但是在實務上，BCNF 被視為大部分應用程式所需的最高階正規形式
    * 是由 Boyce 和 Codd 於 1974 年所提出來的 3NF 的改良式，其條件比 3NF 更加嚴苛，因此每一個符合 BCNF 的關聯一定也是 3NF
    * BCNF 的規則
      * 如果資料表的「主鍵」只由「單一欄位」組合而成，則符合第三階正規化的資料表，亦符合 BCNF(Boyce BCNF(Boyce-Codd Normal Form) Normal Form)正規化
      * 如果資料表的「主鍵」由「多個欄位」組成(又稱為複合主鍵)，則資料表就必須要符合以下條件，我們就說這個資料表符合BCNF(Boyce BCNF(BoyceCodd Normal Form) Normal Form)正規化的形式
        * 符合3NF 的格式。
        * 「主鍵」中的各欄位不可以相依於其他非主鍵的欄位
* 補圖
<br>


## SQL：結構化查詢語言(Structured Query Language)
* 類型：
  * Transact-SQL (又稱T-SQL)
    * 是在 Microsoft SQL Server 和 Sybase SQL Server 上的 ANSI SQL 實作
  * PL-SQL (Procedural Language-SQL)
    * 是甲骨文公司專有的 SQL 擴展語言
* 名詞：
  * DDL (Data Definition Language)：對資料庫物件 (如資料表，預存程序，函式或自訂型別等) 的新增、修改和刪除 (Create、Alter、Drop) 都使用此語法
  * DML (Data Manipulation Language)：又稱 CRUD (Create/Retrieve/Update/Delete) 功能，意指資料的新增、擷取、修改、刪除 (Select、Insert、Delete、Update) 四個功能
  * DCL (Data Control Language)：由資料庫所提供的保安功能，對於資料庫與資料庫物件的存取原則與權限 (Grant、Deny、Revoke)，都由 DCL 定義之
* 函式：
<table border="1" width="40%">
    <tr>
        <th width="10%">函式</a>
        <th width="10%">描述</a>
        <th width="10%">函式</a>
        <th width="10%">描述</a>
    </tr>
    <tr>
        <td> AVG </td>
        <td> 平均值 </td>
        <td> COUNT </td>
        <td> 計數 (不含Null) </td>
    </tr>
    <tr>
        <td> FIRST </td>
        <td> 第一個記錄的值 </td>
        <td> SUM </td>
        <td> 求和 </td>
    </tr>
    <tr>
        <td> MAX </td>
        <td> 最大值 </td>
        <td> MIN </td>
        <td> 最小值 </td>
    </tr>
    <tr>
        <td> STDEV </td>
        <td> 樣本標準差 </td>
        <td> STDEVP </td>
        <td> 總體標準差 </td>
    </tr>
    <tr>
        <td> VAR </td>
        <td> 樣本方差 </td>
        <td> VARP </td>
        <td> 總體方差 </td>
    </tr>
    <tr>
        <td> UCASE </td>
        <td> 轉化為全大寫字母 </td>
        <td> LCASE </td>
        <td> 轉化為全小寫字母 </td>
    </tr>
    <tr>
        <td> MID </td>
        <td> 取中值 </td>
        <td> LEN </td>
        <td> 計算字串長度 </td>
    </tr>
    <tr>
        <td> INSTR </td>
        <td> 獲得子字串在母字串的起始位置 </td>
        <td> FORMAT </td>
        <td> 字串格式化 </td>
    </tr>
    <tr>
        <td> LEFT </td>
        <td> 取字串左邊子串 </td>
        <td> RIGHT </td>
        <td> 取字串右邊子串 </td>   
    </tr>
    <tr>
        <td> ROUND </td>
        <td> 數值四捨五入取整 </td>
        <td> MOD </td>
        <td> 取餘 </td>   
    </tr>
    <tr>
        <td> NOW </td>
        <td> 獲得當前時間的值 </td>
        <td> DATEDIFF </td>
        <td> 獲得兩個時間的差值 </td>   
    </tr>
</table>
<br>


## DataBase 說明
* 中文字
  * 編碼
    * GBK編碼：雙位元組，換句話說：1個中文字相當於2個字元
    * UFT-8編碼：中文使用24位(三個位元組)來編碼，換句話說：1個中文字相當於3個字元
    * Big5編碼：1個中文字相當於2個字元
      <table border="1" width="50%">
        <tr>
          <th width="5%">型態</a>
          <th width="5%">MSSQL</a>
          <th width="5%">Oracle</a>
          <th width="5%">Postgresql</a>
          <th width="5%">MySQL</a>
          <th width="25%">備註</a>
        </tr>
        <tr>
          <td> char </td>
          <td>  </td>
          <td> 3個位元組 <br>
               CHAR(byte/char) </td>
          <td> 3個位元組 </td>
          <td>  </td>
          <td> 定長，字元數沒有達到最大值則使用空白填充，CHAR的效能會比VARCHAR快 </td>
        </tr>
        <tr>
          <td> varchar </td>
          <td> 2個位元組 </td>
          <td> 3個位元組 </td>
          <td> 3個位元組 <br> 
               但設置varchar(n)：無論存字母、數字、其它符號、中文字，長度最大為n個 </td>
          <td> 2個位元組 </td>
          <td> 變長，字元最大數有限制， VARCHAR比CHAR節省空間 </td>
        </tr>
        <tr>
          <td> varchar2 </td>
          <td>  </td>
          <td> 3個位元組 <br>
               VARCHAR2(byte/char) </td>
          <td> --- </td>
          <td>  </td>
          <td> 變長，把空白轉為NULL值，當資料經常需要修改成不同長度時，VARCHAR2會做成遷移(ROW MIGRATION)引起不必要的I/O </td>
        </tr>
        <tr>
          <td> text </td>
          <td>  </td>
          <td>  </td>
          <td>  </td>
          <td>  </td>
          <td> 變長，無長度限制 </td>
        </tr>
        <tr>
          <td> nchar </td>
          <td>  </td>
          <td>  </td>
          <td>  </td>
          <td>  </td>
          <td> 定長，專為unicode而設計，2個位元組存放一個字元(不管字元或漢字) </td>
        </tr>
        <tr>
          <td> nvarchar </td>
          <td> 1個字元數 </td>
          <td> --- </td>
          <td>  </td>
          <td>  </td>
          <td> 變長，專為unicode而設計，長度定義的是字元數，2個位元組存放一個字元(不管字元或漢字) </td>
        </tr>
        <tr>
          <td> nvarchar2 </td>
          <td> --- </td>
          <td> 2個位元組 </td>
          <td>  </td>
          <td>  </td>
          <td> 變長，專為unicode而設計，長度定義的是字元數 </td>
        </tr>
        <tr>
          <td> ntext </td>
          <td>  </td>
          <td>  </td>
          <td>  </td>
          <td>  </td>
          <td> 變長 </td>
        </tr>
      </table>
  * 一個中文字的儲存位元
* 英文字母：相當於1位元組
* 數字：相當於1位元組
  * Transact-SQL 
    * decimal[ ( p[ , s] ) ] 和 numeric[ ( p[ , s] ) ]：固定有效位數和小數位數的數字，其中 p 為有效位數， s 為小數位數， 0 <= s <= p
    * 從 decimal 或 numeric 轉換成 float 或 real 可能會導致有效位數的遺失，而從 int、smallint、tinyint、float、real、money，或 smallmoney 轉換成 decimal 或 numeric 可能會導致溢位
    * 範例：常數 12.345 會轉換成有效位數 5、小數位數 3 的 numeric 值
      * Oracle：設欄位字元型別為 Number(a, b)，其中 a>b，在 insert 資料時，整數部分長度最大不能超過 a-b，小數部分長度如果大於 b，則擷取 b 長度的小數存入資料庫，其餘的會被捨棄。
      * SQL Server：
        * numeric 和 decimal 資料類型的預設最大有效位數為 38。 在舊版的 SQL Server 中，預設的最大值是 28
        * 在將數字轉換成有效位數與小數位數較小的 decimal 或 numeric 值時會使用四捨五入。相反地，如果 SET ARITHABORT 選項是 ON，SQL Server 會在發生溢位時產生錯誤。若只是流失有效位數與小數位數還不足以產生錯誤
        * 在 SQL Server 2016 (13.x) 之前，float 值轉換至 decimal 或 numeric，就會限制為只有 17 個有效位數的值。任何小於 5E-18 (當設定使用 5E-18 科學記號標記法或 0.0000000000000000050000000000000005 十進位標記法時) 的 float 值都會捨去為 0
* 目前使用的 DataBase 
  * Oracle為「TRADITIONAL CHINESE_TAIWAN.AL32UTF8」，故中文字相當於3個字元
    * 語法：select userenv('language') from dual;
  * SQL Server(目標系統)為簡體中文GBK
    * 語法：select COLLATIONPROPERTY('Chinese_PRC_Stroke_CI_AI_KS_WS','CodePage')
    * 結果
      <table border="1" width="40%">
        <tr>
          <th width="10%">代碼</a>
          <th width="10%">語言</a>
          <th width="10%">代碼</a>
          <th width="10%">語言</a>
        </tr>
        <tr>
          <td> 936 </td>
          <td> 簡體中文GBK </td>
          <td> 950 </td>
          <td> 繁體中文BIG5 </td>
        </tr>
        <tr>
          <td> 437 </td>
          <td> 美國/加拿大英語 </td>
          <td> 932 </td>
          <td> 日文 </td>
        </tr>
        <tr>
          <td> 932 </td>
          <td> 日文 </td>
          <td> 949 </td>
          <td> 韓文 </td>
        </tr>
        <tr>
          <td> 866 </td>
          <td> 俄文 </td>
          <td> 65001 </td>
          <td> unicode UFT-8 </td>
        </tr>
      </table>
<br>


## MySQL Server 安裝與配置
* 安裝：確認安裝 MySQL Server 與 ODBC 連接器的支援版本
  * 從 https://dev.mysql.com/downloads/installer/ 下載 MySQL 8 Windows Installer，並執行它
    * 選擇作業系統
    * 進入下載頁面：注意這裡有分成 web 版跟一般版，選擇一般版即可，不用註冊也可以。選擇後，便會開始下載
    * 一直選擇下一項即可，預設的安裝通常都是最輕量化、最沒有額外套件的。唯一重要：一定要把 Root 的密碼設定好
  * 在設定安裝期間，依序選取【自訂】和【MySQL伺服器】，以及要安裝的【連接器/ODBC】。確定 ODBC 連接器符合已安裝 MySQL Server (x86 或 x64) 的位元
  * 完成 MySQL Server 的安裝
* 配置
  * 在文字編輯器中開啟下列檔案：C:\ProgramData\MySQL\MySQL Server 8.0\my.ini
  * 尋找並編輯下列配置，或將它附加至 my.ini 檔案的【mysqld】區段：
    ```
    max_allowed_packet=33M
    ```
    * 針對 MySQL 8，必須設定下列變數：
      ```
      log_bin_trust_function_creators=1
      --或停用二進位記錄
      log_bin=0
      ```
    * 若為 MySQL 5.6.20 與 5.6.21 (可以使用 mysql --version 判斷 MySQL 版本)：
      * innodb_log_file_size 必須設定為至少 200 MB，但不超過 3000 MB
        ```
        innodb_log_file_size=200M
        ```
    * 若為 MySQL 5.6.22 和支援的更新版本 (包括第 8 版)：
      * innodb_log_file_size*innodb_log_files_in_group 必須設定至少為 200 MB，其中 innodb_log_files_in_group 的最小值為 2，最大值為 100，且值必須為整數
        ```
        innodb_log_file_size=100M
        innodb_log_files_in_group=2
        ```
  * 儲存並關閉 my.ini 檔案
  * 開啟命令提示字元，然後輸入下列命令，以重新啟動 MySQL 伺服器並套用配置 (處理程序名稱視 MySQL 的版本而定，如 8.0 = mysql80 等)
    ```
    net stop mysql80
    net start mysql80
    ```
  * 在命令提示字元中輸入下列命令，檢查 MySQL 伺服器是否正在執行中：
    ```
    sc query mysql80
    ```
<br>


## 參考資料
* [資料庫理論與實務](http://spaces.isu.edu.tw/upload/19225/0/news/postfile_174.pdf)
* [NoSQL資料庫](https://www.ithome.com.tw/news/92507)
* [資料庫正規化](http://cc.cust.edu.tw/~ccchen/doc/db_04.pdf)
* [第十章 資料庫邏輯設計](http://www.tsnien.idv.tw/DataBase_WebBook/chap10/10-5%20%E6%AD%A3%E8%A6%8F%E5%8C%96%E6%AD%A5%E9%A9%9F.html)
* [Transact SQL Transact SQL 語法介紹](https://www.taisugar.com.tw/Upload/UserFiles/ServicePlace/133/633924063523432100.pdf)
* [MySQL Server 安裝與配置](https://help.eset.com/esmc_install/72/zh-TW/mysql_windows.html)
* [MySQL 下載安裝步驟的心得筆記](https://clay-atlas.com/blog/2019/11/16/mysql-mysqlworkbench-tutorial-download-install-steps/)
* [Windows 上的 MySQL 安裝教學](https://jerrynest.io/windows-mysql-installer/)
* [Oracle中文字如何計算長度](http://alexlucy99.blogspot.com/2015/03/oracle.html)
* [檢視MySQL和SQL Server資料庫的預設編碼方法](https://www.itread01.com/p/1159234.html)
* [★編碼問題之重要文章](https://codingnote.cc/zh-tw/p/141295/)
* [MySQL計算字串長度及字串位元組數](https://louis176127.pixnet.net/blog/post/134867546)
* [PostgreSQL：字元-型別及函式](https://iter01.com/563047.html)
* [Oracle [char、nchar、varchar、varchar2、nvarchar] 資料類型的區別](http://wupeiting.blogspot.com/2010/08/oracleoracle-charncharvarcharvarchar2nv.htm)
* [Transact-SQL](https://docs.microsoft.com/zh-tw/sql/t-sql/data-types/decimal-and-numeric-transact-sql?view=sql-server-ver15)
* [認識 decimal 和 numeric](http://sharedderrick.blogspot.com/2011/08/decimal-numeric.html)
