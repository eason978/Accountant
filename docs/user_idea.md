我想開發一套智能記帳軟體-Accountant，能夠

1. 包含一般的記帳軟體功能 (請參考firefly iii的功能)
    1. 使用者登入
    2. 多國貨幣
    3. 對帳機制, 帳務平衡機制
    4. 支援category, group category, 一個category可以允許出現在多個group category(e.g 燃料稅可以包含在group 稅務, 也可以包含在group 車子)
    5. 有tag功能, 可以針對交易紀錄添加tag
    6. 資料庫schema請先參考Firefly iii作為基礎, 在按照後面的需求來調整設計
2. 基於Firefly iii, Accountant能夠作為Firefly iii的前端, 實作自動化記帳, 將帳務資料匯入Firefly iii
3. 自動記帳是透過銀行對帳單，信用卡帳單，電子支付交易紀錄, 可以AI辨識出交易紀錄，並匯入Firefly iii, 這些檔案可以是PDF(有可能需要密碼, 要提示使用者輸入), PNG/JPG圖檔
4. 自動記帳時, 需要能提供mapping機制, 可以從來源資料mapping出account, category, expense account, tag…等需要的欄位
5. 自動記帳的功能, 要能提供training mode, 讓使用者針對自己的銀行對帳單, 透過prompt來提高辨識精準度, 並且要能儲存不同銀行的對應prompt
6. 每筆帳務交易, 都需要有一欄raw data來呈現出紀錄帳務時的raw data, e.g. web/富邦信用卡202504對帳單/優食-星巴克
7. Accountant跟使用者互動的介面有
    1. web 
        1. 提供一般記帳軟體會有的功能(帳務查詢, 產生報表資訊, 帳戶設定)
        2. 能夠上傳有交易紀錄的檔案以供自動化記帳. 自動化記帳中間過程如需要與使用者互動, 也要能透過web
        3. 要能跟根據使用者的螢幕解析度, 都能提供適合的UI
    2. chatbot, 預設為Line以及Telegram, 主要是作為chatbot cli的命令介面, 可以做到
        1. 一般記帳軟體的大部分功能(帳務查詢, 產生報表資訊, 帳戶設定)
        2. 能夠上傳有交易紀錄的檔案以供自動化記帳. 自動化記帳中間過程如需要與使用者互動, 也要能透過chat bot
        3. chatbot cli的設計指令盡量精簡, 盡量以提示符號加上一個字母當作指令, 再配上參數
        4. chatbot 能夠支援輸入自然語言, 讓ai去做語意辨識達到操作
    3. email信箱monitor
        1. 可以定時monitor使用者信箱, 如果有銀行對帳單, 電子帳單, 消費紀錄, 就觸發自動記帳
8. 開發環境, 
    1. 請先以能夠架設在雲端服務, 並且評估10人內可做到無需費用就可以營運的平台
    2. 辨識帳單, 交易紀錄交給AI API, 但請保留彈性可以改由文件辨識service + AI API
    3. 選擇開發stack, 盡量考量能在RK3566 + 4GB的ARM SBC上運行架設