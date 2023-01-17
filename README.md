# DataBase

## 名詞解釋
* query：指的是對資料庫作查詢時的語句
* transaction：交易功能，有些流程會一次綁定多個 query ，而 transaction 就是設定說，一定要每個 query 都正確才會全部 query 被真正執行，如果有任何錯誤，就全部 query 執行結果都捨棄
* rollback：取消這次所有的 SQL 查詢更新結果
<br>


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
* 常見資料庫系統
  <table border="1" width="30%">
    <tr>
        <th width="5%">資料庫系統</a>
        <th width="10%">優點</a>
        <th width="10%">缺點</a>
        <th width="5%">軟體介面</a>
    </tr>
    <tr>
        <td> MySQL </td>
        <td> 1.開放原始碼，更新快速 <br>
             2.相容於各個不同的程式語言、作業系統 <br>
             3.具有『多執行緒』，能充分利用資源運算 <br>
             4.社群活躍，資源眾多 </td>
        <td> 1.性能較差，適合中小型應用程式，但在 8.0 更新後，會相較舊版提升 1 倍以上的效能 <br>
             2.安全機制相較其他資料庫是較薄弱的 </td>
        <td> MySQL Workbench 或 PHPmyAdmin </td>
    </tr>
    <tr>
        <td> PostgreSQL </td>
        <td> 1.更加開放，貼近社群 <br>
             2.商業應用導向，擁有更嚴格的測試驗證和設計機制 <br>
             3.Store Procedure 和 View 功能強化 <br>
             4.地理結構資料類型：提供專屬的資料類型、相關的資料庫函式 </td>
        <td> 1.結構龐大：對於較小型的伺服器是個負擔 <br>
             2.複雜的查詢會導致效能低落：主要是因為 PostgreSQL 軟體本身結構的緣故 </td>
        <td> pgadmin 或 DBeaver </td>
    </tr>
    <tr>
        <td> Microsoft SQL Server </td>
        <td> 1.工具整合性：微軟生態系 <br>
             2.使用的學習曲線低：不需要一些繁瑣的設定 <br>
             3.嚴格的交易安全與控制 <br>
        <td> 1.封閉的使用和開發環境：商用版限定在 Windows 平台上為主 <br>
             2.較為笨重 </td>
        <td>  </td>
    </tr>
    <tr>
        <td> Oracle Database </td>
        <td> 1.極高的安全性：具有最高認證級別的ISO標準認證 <br>
             2.效能出色：從事各種大型運算或查詢上，是經過 TPC 組織(專門執行商用負載)的認證 <br>
             3.功能齊全、強大：具有多種資料儲存格式可以選擇，還有各式能夠自行制定的功能，如同義詞、套件等等不同的模塊 <br>
        <td> 1.使用成本昂貴：相對應的硬體設施也有一定的要求 <br>
             2.學習成本高：新手要快速學會核心的應用比較吃力些 </td>
        <td>  </td>
    </tr>
  </table>
<br>


# NoSQL (Not Only SQL)
* 多用於前端
* 類型
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


# 資料庫正規化
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


## GreenPlum
* 查詢欄位資訊
  * 參考資料
    * [【MSSQL、PostgreSQL】列出資料表的欄位與資料型態](https://ryan-tw.blogspot.com/2015/04/postgresql.html)
    
  * 語法
    ```
    SELECT 
         D.table_catalog       as schemas_nm
       , D.table_schema
       , D.table_name         
       , D.ordinal_position  
       , D.column_name       
       , D.data_type 
       , D.character_maximum_length
       , D.character_octet_length
       , D.numeric_precision
       , D.numeric_scale
       , D.is_nullable
       , D.column_default
       , B.description
    FROM information_schema.columns D 
    LEFT JOIN pg_catalog.pg_description B 
      ON 1=1  
     AND D.ordinal_position = B.objsubid
    WHERE D.table_schema = 'SCHEMA'
      AND D.column_name = '欄位名'
    ```
* 查詢所有 Table name
  * 參考資料
    * [Postgres SQL 用 SELECT語法取得Table Schema](https://akuma1.pixnet.net/blog/post/358796858-postgres-sql-%E7%94%A8-select%E8%AA%9E%E6%B3%95%E5%8F%96%E5%BE%97table-schema)
    * [Choosing the Table Storage Model](https://gpdb.docs.pivotal.io/6-5/admin_guide/ddl/ddl-storage.html#topic37)
  * 語法
    ```
    SELECT 
         A.schema
       , A.name
       , A.owner
       , A.type
       , B.description
    FROM (
         SELECT 
              n.nspname as schema
            , c.relname as name
            , CASE c.relkind WHEN 'r' THEN 'table' 
                             WHEN 'v' THEN 'view' 
                             WHEN 'm' THEN 'materialized view' 
                             WHEN 'i' THEN 'index' 
                             WHEN 'S' THEN 'sequence' 
                             WHEN 's' THEN 'special' 
                             WHEN 'f' THEN 'foreign table' 
              END as type
            , pg_catalog.pg_get_userbyid(c.relowner) as owner
            , relfilenode
         FROM pg_catalog.pg_class c
         LEFT JOIN pg_catalog.pg_namespace n 
           ON n.oid = c.relnamespace
         WHERE
               c.relkind IN ('r','s','') 
           AND n.nspname !~ '^pg_toast' 
           AND n.nspname ~ '^(public)$'
         ORDER BY 1,2
     ) A 
     LEFT JOIN pg_catalog.pg_description B 
       ON A.relfilenode = B.objoid 
      AND B.objsubid = 0
    ```
    
    ```
    select 
         b.nspname
       , a.relname as Tablename
       , case c.columnstore
              when 'f' then 'Row Orientation'
              when 't' then 'Column Orientation'
         end as TableStorageType
       , case COALESCE(c.compresstype,'')
              when '' then 'No Compression'
              else c.compresstype
         end as CompressionType
       , compresslevel   
    from pg_class a
         , pg_namespace b
         , pg_appendonly c
    where b.oid = a.relnamespace 
      and a.oid = c.relid
    ```
<br>


## Oracle 
* NBU 來不及備份，發生 delete transaction log 的情況
  * 影響：archivelog delete 後該 DB 將無法 Restore 到 archivelog 的對應時間點，作法
    * 檢視是否有使用「delete * from Table」的方式清空 table (作為暫存資料的table)，有的話改用「truncate table 方式」
    * 考慮將 table 改為 nologging table (外加 insert 搭配 append 方式)，可減少因 insert/delete/update 等 DML 而產生的 transaction log 量，參考資料：https://www.cnblogs.com/andy6/p/7484209.html
* 查詢欄位資訊
  * 參考網頁
    * [Oracle查詢資料表結構/欄位/型別/大小](https://www.796t.com/content/1547245448.html)
  * 語法
    ```
    SELECT 
         A.OWNER as Owner
       , A.TABLE_NAME as 表格名稱
       , A.COLUMN_ID as 欄位代碼
       , A.COLUMN_NAME as 欄位名
       , A.DATA_TYPE as 資料型別
       , A.DATA_LENGTH as 長度
       , A.DATA_PRECISION as 整數位
       , A.DATA_SCALE as 小數位
       , A.NULLABLE as 允許空值
       , A.DATA_DEFAULT as 預設值
       , B.COMMENTS as 備註  
    FROM ALL_TAB_COLUMNS A
    JOIN ALL_TABLES T 
      ON A.OWNER = T.OWNER 
     AND A.TABLE_NAME = T.TABLE_NAME
    LEFT JOIN ALL_COL_COMMENTS B
      ON A.OWNER = B.Owner
     AND A.TABLE_NAME = B.TABLE_NAME
     AND A.COLUMN_NAME = B.COLUMN_NAME 
    WHERE 1=1
      AND A.OWNER = 'SCHEMA'
      AND A.COLUMN_NAME = upper('欄位名')
    ORDER BY A.TABLE_NAME, A.COLUMN_ID
    ```
<br>


## Comparing backup types
<table border="1" width="45%">
        <tr>
          <th width="5%"> Type of backups </a>
          <th width="5%"> Describe </a>
          <th width="10%"> Benefit s</a>
          <th width="10%"> Drawbacks </a>
          <th width="15%"> SQL </a>
        </tr>
        <tr>
          <td> Full </td>
          <td> ● 整個數據集的完整副本，提供最好的保護 </td>
          <td> ● Provides full copy of data set <br>
               ● Offers arguably best protection </td>
          <td> ● Time-consuming <br>
               ● Requires lots of storage space </td>
          <td> ● --truncate production table-- <br>
               ● --insert target table-- </td>
        </tr>
        <tr>
          <td> Incremental </td>
          <td> ● 為了提高備份速度並減少執行完整備份所需的存儲空間，僅備份自上次備份以來已更改的數據 </td>
          <td> ● Less time and storage space than full backup </td>
          <td> ● Time-consuming to restore <br>
               ● Need all the backups in backup chain to restore </td>
          <td> ● --create temp table and insert table-- <br>
               ● --clean source data-- <br>
               ● --create temp table and insert table-- <br>
               ● --insert temp table-- <br>
               ● --create production table backup-- <br>
               ● --insert all production data into production backup table-- <br>
               ● --truncate production table-- <br>
               ● --insert target table-- <br>
               ● --drop temp table-- </td>
        </tr>
        <tr>
          <td> Differential (差異備份) </td>
          <td> ● 自上次完整備份以來更改的所有數據 </td>
          <td> ● Shorter restore time than incremental </td>
          <td> ● Can grow to much bigger size than incremental </td>
          <td>  </td>
        </tr>
        <tr>
          <td> Synthetic full (合成完整備份) </td>
          <td>  </td>
          <td> ● Reduced restore time <br>
               ● Less bandwidth usage </td>
          <td> ● Newer, so not as well-known </td>
          <td>  </td>
        </tr>
        <tr>
          <td> Incremental-forever (永久增量備份) </td>
          <td>  </td>
          <td> ● Availability of data <br>
               ● Automated restoration process </td>
          <td> ● Newer, so not as well-known <br>
               ● Need all the backups in backup chain to restore </td>
          <td>  </td>
        </tr>
</table>        
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
* [Comparing backup types](https://www.techtarget.com/searchdatabackup/tip/Data-backup-types-explained-Full-incremental-differential-and-incremental-forever-backup)
* [資料庫 - 介紹與比較](https://ithelp.ithome.com.tw/articles/10206222)
