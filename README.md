# NYCU Thesis Template

此專案為「國立陽明交通大學」碩博士論文模板。

## Installation

> 關於安裝資訊：https://www.latex-project.org/get/#tex-distributions

* Windows
    * 安裝 [MiKTeX](https://miktex.org/)
* MacOS
    * 安裝 [MacTeX](http://www.tug.org/mactex/)
* Linux
    * 安裝 [TeXLive](https://www.tug.org/texlive/)
* Online LaTeX Service
    * [Overleaf](https://www.overleaf.com)

## Usage

0. 下載此專案。
1. 執行以下指令進行編譯。
    ```bash
    # Make sure your current directory is correct
    $ make
    ```
    * 需等待 2-3 秒，若編譯成功，會在最後一行出現以下範例訊息，而不會有任何錯誤訊息。
        ```bash
        ...
        Output written on main.pdf (23 pages).
        ```
    * 編譯成功後會自動生成 PDF 檔案 `main.pdf`。
2. 如何移除編譯過程所產生的中間檔案 (e.g., `main.aux`, `main.bbl`, `main.blg`, etc.)？
    ```bash
    # Make sure your current directory is correct
    $ make clean
    ```
    * 中間檔案為非必要檔案，已經寫入 `.gitignore` 中。
3. 如何選擇輸出格式？
    * 可選格式
        * 碩/博士論文 ( **`master`**/`phd`)
        * 中/英文 (**`en`**/`zh`)
        * 編輯中/初稿/定稿 (`review`/**`draft`**/`final`)
        * 印刷/圖書館上傳格式 (**`print`**/`upload`)
        * 有/無浮水印 (`watermark`)
        * 是/否引入照片與審定書等文件(`binding`)
            * 只有`final`才會有binding效果            
        * 粗體為預設格式
    * 修改 [`main.tex: 11`](main.tex#L11)
        * 將欲輸出的格式填入方框中以逗號隔開，如下例為「碩士中文論文印刷定稿」。
            ```latex=11
            \documentclass[master, zh, final, print]{Class/NYCUtran}
            ```
4. 由於陽明交大尚未決定校徽，故目前繳交之論文仍不需要附上浮水印，然未來仍有加上浮水印之需求，故先將原專案之交大浮水印附上，並設定為不須輸出浮水印，未來只需更改原圖檔為新校徽即可繼續使用。
5. 如有新增檔案，需於`main.tex`中對應的位置新增引入。
    * 如新增章節`5-Chapters/6-Other.tex`
        ```latex=77
        % 於對應位置 (Line 79)新增引入。
        \input{5-Chapters/5-Conclusion}
        \input{5-Chapters/6-Other}
        ```

## Directory Structure

```bash
# In alphabetical order
nycu-thesis-template
├── 0-Cover/                        # 0-論文封面文件 (自行編輯)
│   └── Spine.docx                  #   書背製作檔 (自行編輯)
├── 1-Cert/                         # 1-論文口試審定書 (可自行新增)
│   ├── .gitkeep
│   ├── 1-Certification-zh.pdf      #   論文口試審定書中文範本 (資科工碩)
│   └── 2-Certification-en.pdf      #   論文口試審定書英文範本 (資科工碩)
├── 2-Auth/                         # 2-論文授權書 (可自行新增)
│   ├── .gitkeep
│   └── 1-Authorization.pdf         #   論文授權書範本
├── 3-Abs/                          # 3-摘要 (自行編輯)
│   ├── 1-Abstract-zh.tex           #   中文摘要 (自行編輯)
│   └── 2-Abstract-en.tex           #   英文摘要 (自行編輯)
├── 4-Ack/                          # 4-誌謝與題獻 (自行編輯)
│   ├── 1-Acknowledgement.tex       #   誌謝頁 (自行編輯)
│   └── 2-Dedication.tex            #   題獻頁 (自行編輯) [博士論文使用]
├── 5-Chapters/                     # 5-論文各節內容 (可自行新增)
│   ├── 1-Introduction.tex
│   ├── 2-RelatedWork.tex
│   ├── 3-Design.tex
│   ├── 4-Evaluation.tex
│   └── 5-Conclusion.tex
├── 6-Bib/                          # 6-參考文獻
│   ├── BSTcontrol.bib              #   IEEE 論文參考書目設定 (不需更動)
│   └── thesis.bib                  #   參考文獻檔 (自行編輯)
├── 7-Appx/                         # 7-附錄 (可自行新增)
│   └── 1-Appx.tex           
├── 8-Author/                       # 8-作者簡歷與著作列表 (自行編輯) [博士論文使用]
│   ├── 1-CV.tex                    #   作者簡歷 (自行編輯) [博士論文使用]
│   └── 2-Publications.tex          #   著作列表 (自行編輯) [博士論文使用]                               
├── Class/                          # * 論文模板 (不需更動)
│   ├── IEEEtran.bst                #   IEEE 論文參考書目樣式 (不需更動)
│   ├── IEEEtrantools.sty           #   IEEE 論文模板樣式指令 (不需更動)
│   ├── NYCUtran.cls                #   國立陽明交通大學碩博論文模板 (不需更動)
│   └── xCJKnumb.sty                #   中文套件 (不需更動)
├── Config/                         # * 相關參數設定
│   ├── config.tex                  #   設定論文標題、作者資訊等 (自行編輯)
│   └── fonts.tex                   #   字型設定 (不需更動)
├── Figurs/                         # * 論文圖片 (可自行新增)
│   └── ...
├── Tools/                          # * 相關小工具 (不需更動)
│   └── ...
├── .gitignore                      # 檔案忽略清單 (不需更動)
├── GNUmakefile                     # 編譯論文檔案所用 (不需更動)
├── LICENSE                         # 專案授權 (不需更動)
├── main.tex                        # 論文主要檔案 (自行編輯)
├── main.pdf                        # 論文輸出檔案
└── README.md                       # 說明文件 (本檔案)
```

## Useful Plugins

* **[LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)** (on [Visual Studio Code](https://code.visualstudio.com/))

## Reference

* [The LaTex Project](https://www.latex-project.org/)
* [CTAN](https://www.ctan.org/)
* [LaTeX Wikibooks](https://en.wikibooks.org/wiki/LaTeX)

## Acknowledgement

* 此模板修改自原[交大模板](https://github.com/yungshenglu/NCTU-Thesis-Template)
  * 原作者：[yungshenglu](https://github.com/yungshenglu)
  * 原模板專案：[yungshenglu/NCTU-Thesis-Template](https://github.com/yungshenglu/NCTU-Thesis-Template)

## License

[GNU GENERAL PUBLIC LICENSE Version 3](LICENSE)