# Linux  
絕對路徑：從根目錄/寫起  
相對路徑：「相對於當前工作目錄的路徑」  
## 特殊的目錄：  
．此層目錄     
．．上一層目錄  
-前一個工作目錄  
~目前使用者身分(所在的家目錄home)  
  
## 重要指令  
cd 變換目錄  
pwd 顯示目前目錄的所在位置  
ls 顯示目錄下的所有檔案  
ls-l 顯示目錄下的所有檔案詳細資訊  
ls-al 顯示目錄下的所有檔案(包含隱藏檔)詳細資訊  
touch 建立檔案  
cp 複製  
cat 查看檔案內容  
vi 編輯檔案  
mkdir 建立一個新目錄  
mkdir-p 同時建立多個目錄  
rmdir 刪除一個裡面是空的目錄  
rm 刪除檔案  
rm-r 強制刪除  
mv 移動，重新命名  
chown 修改檔案或目錄的擁有者及群組  
  
## 更改使用者權限及目錄權限  
chmod 664 test.txt  
 rw-rw-r--  
 |  身份  	| 權限 	|   分數   	|
|:------:	|:----:	|:--------:	|
|  owner 	|  rw- 	| 4+2+0 =6 	|
|  group 	|  rw- 	| 4+2+0 =6 	|
| others 	|  r-- 	| 4+0+0 =4 	|  
  
|     字元     | 權限分數 |
|:------------------:|:--------:|
|   r 可讀取(read)   |     4    |
|   w 可寫入(write)  |     2    |
|  x 可執行(execute) |     1    |
|    - 無權限        |     0    |  
  
|                |        擁有者(user)        |      所屬群組(group)      |     其他使用者(other)     |
|:---------------:|:--------------------------:|:------------------------:|:------------------------:|
|        d       |             rwx           |             r-x            |            r-x           |
| 代表是一個目錄  | 具備讀、寫、執行權限        | 只擁有讀、執行權限          | 只擁有讀、執行權限          |  
  
## 編輯文檔  
### nano  
ctrl+c:顯示游標所在  
ctrl+w:查詢命令  
### vi/vim  
一般模式: 上下左右進行游標移動、刪除字元及複製貼上檔案資料  
編輯模式:編輯文字(i鍵進入編輯模式，esc退出編輯模式) 
命令列模式(!代表強制)   
|:w|編輯資料寫入硬碟檔案中|  
|:--:|:-----------:| 
|:w!|檔案屬性 只讀，強制寫入該檔案|  
|:q|離開|
|:q!|強制離開埠儲存檔案|  
|:wq|儲存後離開|  
## 壓縮檔案  
在記憶體很小的機器(<128MB)解壓縮時，選擇gzip  
在很簡單、沒有什麼工具可用的機器解壓縮，選擇gzip  
節省頻寬、縮短下載所需時間，選擇xz  
最好壓縮率，選擇tar.xz  
### gzip  
壓縮:gzip FileName  
解壓縮:gunzip FileName.gz    gzip-d FileName.gz  
### xz  
壓縮:xz-z FileName  
解壓縮:xz-d FileName.xz  
### tar.gz  
壓縮:tar-zcvf FileName.tar.gz DirName  
解壓縮:tar-zxvf FileName.tar.gz  
## 檔案搜尋
### find  
-size EX:大於500M的檔案 -size +500M  
-name EX:照片的檔案  -name".jpg"  
-type EX: -type f 一般檔案; -type d 一般目錄  
-user EX:同時找兩個擁有者的檔案  -user user1-o-user user2  
### which filename  
-a: 顯示被找到命令執行檔的完整路徑  
-n: 指定文件名長度  
-p:跟-n相同，但包含文件的路徑  
-w:指定輸出欄位寬度  
-v:顯示版本訊息  
## 檔案內容查閱  
### cat(從第一行顯示檔案內容、形成新檔案)  
eg. cat-n file1>file2 把1的檔案內容加上行號後輸入2的檔案  
-n由1開始對所有輸出的行數編號  
'>'將多個文件覆蓋到目標文件中  
'>>'將多個文件追加到目標文件中，不覆蓋  
### tac(從最後一行開始顯示)  
eg. tac-r-s'x\|[^x]' test.log  一個間著一個字符的反轉一個文件  
-r將分隔符作為基礎正規表達  
-s使用String最為分隔符代替默認的換行符  
### more(一頁一頁的顯示檔案內容)  
eg. more+20 testfile 從20行開始顯示文檔內容  
enter向下n行  
crtl+f/spece向下滾動一屏  
ctrl+b返回上一屏  
### less(既可向前又可向後翻頁閱讀檔案)  
eg. ps-ef less  
ps查看進程訊信息並通過less分頁顯示  
j 下一行  
k 上一行  
G 移動到最後一行  
g 移動到第一行  
### head(取出前面幾行，預設10行)  
-n 後面接數字，代表幾行  
### tail(取出後面幾行，預設10行)  
-n 後面接數字，代表幾行  
(-n+20 只列出20行以後的資料)  






           
