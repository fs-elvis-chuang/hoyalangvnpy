💢注意：執行情境有兩種 1. 開發階段 2. 產品階段
🚩前置準備
    無論選擇何種情境來執行，先開啟一個PowerShell。
    首先清除先前建置出來的Image與Container內容，確保我們Docker環境是乾淨的。
    ==>【docker system prune -af】 
    ==> 該指令可以清除Desktop Docker上的Image與Container。
1. 開發環境：
    在專案根目錄下執行【code .】

2. 生產環境：
    進入道【專案目錄】下的〔.devcontainer目錄〕下執行
    a. 建立Image
        【docker compose -f .\docker-compose.yml --env-file var_dev.env build】
    b.運行Image
        【docker compose -f docker-compose.yml up -d】

🚩Python版本指定
    請參考〔https://www.python.org/doc/versions/〕版號列表選取版號
    然後再至Dockerfile中修改 conda install -y python=3.10.15 版號
    -- 【python --version】 可以獲取目前的版號
    -- 【pip --version】    可以獲取目前套件安裝路徑
________________________________________________________________________________
如何準備GitHub上初版程式庫〔Repository〕
    1. 在GitHub上面建立一個全空的Repo，該Repo的命名是日後Clone下來時候程式碼的根目錄名稱。
        建議：全小寫英、數文字，
        例如： sample_repo 。
        💢複製該Repo的URL位置。
    2. 在本地端：請用【月-日-時分】格式建立一個目錄，我們將要此目錄來下載剛剛建立的Repo。
        例如：08-23-2237
    3. 在本地端：根據剛剛建立的目錄，開啟一個PowerShell。
        以下指令執行，將以此PowerShell下執行。
    4. 【git clone URL】，例如：git clone https://github.com/fs-elvis-chuang/sample_repo.git 
		並且進入該下載下來repo目錄，【cd sample_repo】
	5. 【 git-crypt init 】
        此指令將建立一個加密、解密的金鑰。
    6. 【 git-crypt export-key G:\我的雲端硬碟\git-crypt-keys\sample_repo.key 】
        備份剛剛建立的金鑰。
    7. 複製一份樣板程式碼到此目錄。並且在PowerShell中執行【docker system prune -af】
		其目的是清空先前的image與container。
    8. 【 code . 】
        開啟 VS Code， 後續的動作將轉換至 VS Code中操作。
    9. 先不要建立該Image與Container。
        應該先決定我們開發環境要使用哪個版本的Python，Image Root密碼。
        決定該開發環境是單一運作程式，還是一群為服務構成架構。諸如此類。
        這些設定在.devcontainer/.env檔案之中。
        如果初版成立，我們可以透過Command Pallete【ctrl+shift+p】搜尋欄輸入〔dev containers〕
        點選"Rebuild and Reopen in Container"
    10. 確認無誤之後，準備將此基礎版的程式碼存入GitHub
        在VS Code的Source Control中將這些相關程式碼commit and Push。
        💢注意：在處理Source Control必須處在本機模式。
        切換方法：在VS Code左下方的〔>< 遠端除錯〕點選項目"Reopen Folder Locally"。
    11. 至GitHub檢視是否有將相關程式碼隱藏起來。
________________________________________________________________________________
________________________________________________________________________________
📌補充說明：


    
			
		
