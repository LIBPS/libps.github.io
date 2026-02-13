# 字典程序(Py Addition)

#### 更新時間：2023/7/21
#### （除了比C++版本UI差，其他都很厲害！————BQ）

```python
import os
def clear_screen():
    if os.name == 'nt':
        _ = os.system('cls')
    else:
        _ = os.system('clear')
def main_screen():
    global gui_beta
    if gui_beta == False:
        clear_screen()
        print(f"""歡迎來到字典程序(py addition)(By:MiXiaozai Studio)\t\t{"debug = True" if debug else ""}

請選擇您的模式(輸入前面的序號)
 s.查字模式
 d.字典附件
 f.更新日誌
 g.製作人員
 h.字典程序設置
 j.指令幫助

當前版本號:{VERSION}
請您輸入模式:""",end="")
        inp = input().lower()
        if inp in ["s", "d", "f", "g", "h"]:# j
            mode = {"s": search, "d": more, "f": log, "g": dev, "h": settings}
            return mode[inp]
        elif inp.startswith("/") or inp == "j":
            if inp == "/debug":
                return F3
            elif inp.startswith("/help") or inp == "j":
                try:
                    input(HELP_DIR[inp[6:]])
                except:
                    try:
                        if inp[5] == " ":
                            input("你要查找的指令未找到")
                        else:
                            input("你在輸入一個指令嗎？如果是，請使用正確的指令格式")
                            main_screen()()
                    except:
                        for i in HELP_DIR:
                            print(HELP_DIR[i])
                        input()
                main_screen()()
            elif inp == "/back":
                clear_screen()
                quit()
            elif inp == "/gui":
                gui_beta = not gui_beta
                main_screen()()
            else:
                input("你在輸入一個指令嗎？如果是，請使用正確的指令格式")
                main_screen()()
        else:
            input("你的輸入有誤")
            main_screen()()
    elif gui_beta == True:
        clear_screen()
        print("窗口模式工作中")
        import easygui as gui
        inp = gui.buttonbox(f"""歡迎來到字典程序(py addition)(By:MiXiaozai Studio)\t\t{"debug = True" if debug else ""}

    注意!!!此功能仍在製作中!!!

    請選擇您的模式
    當前版本號:{VERSION}
    請您選擇模式:
        """, "字典程序(py addition)(By:MiXiaozai Studio)", ["查字模式", "字典附件", "更新日誌", "製作人員", "字典程序設置"])
        if inp == None:
            return settings()
        return {"查字模式":search, "字典附件":more, "更新日誌":log, "製作人員":dev, "字典程序設置":settings}[inp]


def search():   
    clear_screen()
    global tone
    max_dis = 90
    if gui_beta == False:
        while True:
            inp = input(f"""請輸入拼音或/help:\t\t\t{f"tone = {tone}    max_dis = {max_dis}" if debug else ""}\n""").lower()

            if inp.startswith("/"):#if it is a command
                if inp[:4] == "/all":
                    cnt = 0
                    from math import ceil                    
                    for items in TEXT.items():

                        cnt += ceil(len(items[1][0]) / 2)
                        print(items[0], end = "")
                        for j in range(0, len(items[1][0]), max_dis):
                            print("\t", end = "")
                            print(items[1][0][j:j+max_dis])
                        
                    input(f"\n總共收錄{cnt}字\n")
                elif inp[:5] == "/help":
                    try:
                        if inp[5] == " ":
                            search_help(inp)
                        else:
                            input("你在輸入一個指令嗎？如果是，請使用正確的指令格式\n")
                    except:
                        search_help(inp)
                elif inp[:5] == "/back":
                    main_screen()()
                elif inp[:5] == "/tone":
                    clear_screen()
                    if tone:
                        input("聲調關")
                    else:
                        input("聲調開")
                    tone = not bool(tone)
                else:
                    input("你在輸入一個指令嗎？如果是，請使用正確的指令格式\n")
            else:
                if TEXT.get(inp) != None:
                    input(TEXT.get(inp)[0] + "\n")
                else:
                    input("你查找的拼音不存在或未收錄\n")
            clear_screen()      
    elif gui_beta == True:
        import easygui as gui
        inp = gui.enterbox("請輸入拼音或/help", "字典程序(py addition)(By:MiXiaozai Studio)", "/help", False)
        gui.msgbox()

def search_help(inp:str):
    try:
        input(HELP_DIR[inp[6:]])
    except:
        if len(inp) > 6:
            input("你要查找的指令未找到")
        else:
            for i in HELP_DIR:
                print(HELP_DIR[i])
            input()

def more():
    clear_screen()
    inp = input("""(1)\t*.md -> *.html\t(注:需要markdown庫;此功能未完成)
(2)\tnltk集合\t(注:需要nltk庫;此功能未完成)
(/back)\t退出
""").lower()
    if inp == "/back":
        main_screen()()
    elif inp == "1":
        more__md_html()
    elif inp == "2":
        more__nltk()
    else:
        more()

def more__md_html():
    clear_screen()
    try:
        import markdown
    except ModuleNotFoundError:
        input("你沒有markdown庫\n") 
        more()   
    input("此功能未製作")
    more()
def more__nltk():
    clear_screen()
    try:
        import nltk
    except ModuleNotFoundError:
        input("你沒有nltk庫\n")
        more()
    try:
        from nltk.corpus import words
    except:
        nltk.download('words')
    print(words.words(language))
    input("此功能棄坑")
    more()

def log():
    clear_screen()
    input("""
[2023/6/13 19:37] 實現了更新日誌,作者名單,第一條指令(/op)(目前沒用)
[2023/6/14 16:05] 實現了查字模式指令(/all)
[2023/6/15 18:19] 查字系統完成,無聲調與C++版本同步更新;有聲調版本基於http://xh.5156edu.com/pinyi.html更新
[2023/6/17 10:53] 實現指令(/debug)和(/tone)刪除指令(/op)
[2023/7/12 15:58] 與C++版本同步更新字庫
[2023/7/19 14:52] 更新字典附件
[2023/7/20 19:45] 加強查字模式指令(/help)
[2023/7/21 10:48] 加強主頁指令(/help)
[2023/8/19 19:28] 更新gui模式的主頁(可在設置打開);把版本號變為alpha0.16
[2023/9/23 **:**] 調整字庫存儲方式;把版本號變為alpha0.17.1
[2023/9/24 13:10] 修復上個更新(/all)無法使用的bug;版本號不變
[2024/2/25 11:45] 正式宣布棄坑(不寫註釋)
""")
    main_screen()()
def dev():
    clear_screen()
    input("""主要開發:Lucas
    
原版製作:BQ
    """)
    main_screen()()
def settings():
    clear_screen()
    inp = input("""g\t打開gui demo(功能製作中)
/back\t退出\n""").lower()
    if inp == "g":
        global gui_beta
        try:
            import easygui
            clear_screen()
        except:
            input("開啓失敗\n")
            settings()
        gui_beta = True
        main_screen()()
        clear_screen()
        input("已結束gui模式\n")
        settings()
    elif inp == "/back":
        main_screen()()
    else:
        settings()
def F3():
    global debug
    if debug:
        input("開發者信息關")
    else:
        input("開發者信息開")
    debug = bool(int(debug) - 1)
    main_screen()()

global path, path_tone, version, debug, tone, help_dir, gui_beta

HELP_DIR = {"all"  :"/all\t在查字模式輸入後輸出所有收錄字",
            "back" :"/back\t退出",
            "help" :"/help\t顯示此列表,單個空格後加指令(不加\"/\")可以精確查找",
            "tone" :"/tone\t在查字模式輸入切換聲調模式(nǐ hǎo => ni3 ha3o)",
            "debug":"/debug\t在主頁輸入切換更多信息顯示"}

TEXT = {
"a"     : ["吖 阿 阿 啊 錒 醃 嗄 "],
"ai"    : ["哎 哀 鎄 埃 挨 皚 癌 欸 矮 藹 靄 艾 磑 砹 愛 嬡 璦 靉 曖 隘 障 "],
"an"    : ["安 按 桉 氨 鵪 諳 盦 銨 俺 埯 唵 岸 按 胺 案 暗 黯 "],
"ang"   : ["骯 卬 昂 盎 "],
"ao"    : ["凹 熬 敖 嶅 嗷 獒 翱 鏖 拗 襖 奧 "],
"ba"    : ["丷 八 仈 巴 叭 朳 玐 吧 岜 扷 芭 夿 疤 柭 釟 蚆 粑 笆 捌 哵 羓 豝 䰾 叐 茇 妭 拔 癹 菝 軷 詙 跋 颰 魃 鼥 把 鈀 鈀 靶 叭 把 伯 弝 壩 爸 杷 垻 罷 耙 跁 鮁 靶 罷 鮁 覇 矲 霸 壩 灞 欛 抜 鎺 鯐 "],
"bai"   : ["挀 掰 白 犤 百 伯 佰 陌 柏 栢 捭 絔 擺 擺 襬 庍 唄 拝 敗 拜 敗 猈 稗 粺 薭 贁 韛 瓸 竡 粨 兡 "],
"ban"   : ["扳 肦 攽 班 般 頒 斑 斒 搬 頒 鳻 瘢 螌 褩 癍 辬 阪 岅 坂 板 版 昄 瓪 鈑 粄 舨 鈑 蝂 魬 闆 辦 半 伴 扮 拌 姅 絆 坢 怑 柈 秚 絆 湴 鉡 靽 辦 瓣 螁 "],
"bang"  : ["邦 幫 垹 梆 捠 浜 邫 幇 幚 縍 幫 鞤 綁 綁 榜 牓 膀 玤 挷 旁 蚌 棒 棓 傍 謗 蒡 搒 塝 稖 膀 蜯 榜 鎊 磅 艕 謗 鎊 "],
"bao"   : ["勹 包 苞 孢 炮 枹 胞 剝 剝 笣 齙 煲 裦 褒 蕔 襃 闁 齙 窇 雹 薄 寶 飽 怉 鴇 保 宲 珤 葆 堡 堢 媬 寚 飽 飹 褓 駂 鳵 鴇 緥 賲 寳 寶 靌 勽 刨 報 抱 鉋 豹 趵 蚫 菢 袌 報 鉋 鮑 骲 髱 暴 虣 鮑 曓 儤 瀑 爆 犦 曝 忁 鑤 佨 藵 "],
"bei"   : ["陂 卑 杯 柸 背 盃 桮 椑 揹 悲 鵯 碑 藣 鵯 北 鉳 貝 狽 孛 邶 貝 牬 昁 苝 備 郥 背 鋇 被 倍 俻 狽 悖 梖 偝 偹 鄁 珼 琲 憊 軰 備 僃 棓 輩 焙 蓓 蛽 碚 愂 禙 犕 褙 誖 鞁 骳 鋇 輩 糒 憊 鞴 鐾 唄 "],
"ben"   : ["奔 泍 賁 犇 錛 錛 本 苯 奙 畚 翉 楍 夯 坌 倴 逩 桳 笨 捹 渀 撪 "],
"bei"   : ["陂 卑 杯 柸 背 盃 桮 椑 揹 悲 鵯 碑 藣 鵯 北 鉳 貝 狽 孛 邶 貝 牬 昁 苝 備 郥 背 鋇 被 倍 俻 狽 悖 梖 偝 偹 鄁 珼 琲 憊 軰 備 僃 棓 輩 焙 蓓 蛽 碚 愂 禙 犕 褙 誖 鞁 骳 鋇 輩 糒 憊 鞴 鐾 唄 "],
"ben"   : ["奔 泍 賁 犇 錛 錛 本 苯 奙 畚 翉 楍 夯 坌 倴 逩 桳 笨 捹 渀 撪 "],
"beng"  : ["伻 祊 奟 崩 繃 閍 絣 痭 嵭 嘣 綳 繃 甭 甮 埄 埲 菶 繃 琫 琣 鞛 迸 泵 蚌 逬 繃 揼 塴 甏 鏰 蹦 鏰 "],
"bi"    : ["皀 屄 偪 逼 毴 楅 榌 豍 鵖 螕 鰏 鎞 鰏 荸 鼻 匕 比 朼 夶 吡 妣 沘 佊 疕 彼 毞 柀 秕 筆 粃 舭 俾 啚 筆 鄙 箄 聛 貏 幣 必 畢 閉 庇 佖 詖 芘 邲 迊 坒 怭 怶 苾 妼 咇 泌 畀 畁 嗶 蓽 陛 賁 毖 柲 珌 疪 秘 鉍 斃 狴 畢 袐 粊 笓 閉 閉 婢 庳 萆 萞 梐 敝 贔 堛 愊 愎 皕 禆 弼 弻 湢 詖 篳 賁 貱 蜌 裨 闢 閟 飶 鉍 潷 滭 嗶 彃 蓖 蓽 腷 睥 睤 痹 痺 煏 熚 碧 蔽 弊 鄪 獙 幣 綼 箅 箆 馝 髲 駜 襅 幤 潷 罼 獘 壁 廦 嬖 避 薜 篦 篳 縪 觱 鮅 蹕 髀 濞 斃 臂 奰 鏎 饆 鄨 璧 繴 襣 襞 鞸 魓 韠 躄 躃 驆 鷝 鐴 贔 朇 鷩 鼊 萙 蛯 嬶 "],
"bian"  : ["邊 炞 砭 籩 萹 編 猵 煸 牑 甂 箯 蝙 糄 編 鞕 鍽 鯿 獱 邉 邊 鞭 鯿 鯾 籩 ", "貶 扁 窆 匾 貶 惼 萹 褊 稨 碥 鴘 藊 ", "卞 弁 抃 汳 汴 苄 釆 忭 玣 變 変 昪 便 覍 徧 遍 緶 揙 閞 辡 諚 緶 艑 辨 辯 辧 辮 辮 辯 變 ", "峅 "],# 1 3 4
"biao"  : ["杓 標 颮 驫 髟 彪 淲 猋 脿 颮 滮 摽 驃 蔈 幖 墂 麃 標 熛 膘 鏢 瘭 磦 飆 飈 儦 颷 謤 藨 瀌 爂 鏢 贆 臕 穮 鑣 飆 飇 飈 飊 鑣 驫 表 婊 裱 諘 錶 褾 檦 俵 摽 鰾 鋲 "],
"bie"   : ["憋 癟 蟞 鱉 癟 鱉 鼈 虌 龞 別 別 莂 蛂 徶 襒 蹩 癟 別 彆 "],
"bin"   : ["邠 玢 賓 彬 梹 椕 儐 斌 濱 繽 賓 賔 豩 檳 璸 鑌 儐 瀕 頻 豳 濱 濵 虨 璸 檳 瀕 霦 繽 蠙 鑌 顮 擯 殯 臏 髩 鬂 擯 殯 臏 髕 鬢 髕 鬢 "],
"bing"  : ["冫 仌 氷 並 冰 兵 屏 栟 掤 檳 丙 邴 陃 苪 怲 抦 秉 昞 昺 炳 柄 屏 餅 綆 眪 蛃 偋 寎 棅 鈵 稟 稟 鉼 餅 餠 鞞 並 幷 並 併 庰 倂 栤 竝 病 窉 傡 摒 誁 鮩 靐 垪 鞆 "],
"bo"    : ["癶 癷 波 撥 玻 餑 缽 盋 砵 哱 剝 般 趵 缽 紴 袰 菠 啵 溊 碆 缽 鮁 僠 蕃 嶓 播 撥 餑 礡 蹳 驋 鱍 仢 伯 駁 孛 肑 瓝 泊 狛 帛 郣 勃 侼 胉 柏 襏 瓟 秡 鈸 鉑 浡 挬 亳 萡 淿 脖 袹 舶 鵓 渤 葧 博 猼 餺 愽 搏 鈸 鉑 鮊 魄 馛 駁 艊 箔 牔 煿 膊 僰 鎛 踣 鋍 馞 駮 鮊 薄 謈 襏 簙 餺 鵓 鎛 嚗 懪 髆 髉 糪 襮 欂 礴 鑮 癷 跛 簸 柏 薄 孹 檗 擘 簸 譒 蘗 畓 蔔 "],
"bu"    : ["逋 庯 峬 鈽 晡 鈽 誧 餔 錻 不 鳪 轐 醭 卜 卟 補 哺 捕 堡 補 鵏 鸔 佈 步 怖 咘 鈈 柨 悑 部 勏 捗 埔 埗 荹 埠 瓿 鈈 蔀 廍 踄 郶 餢 篰 簿 巭 "],
"e"     : ["額 呃 餓 訛 惡 鵝 諤 噩 厄 顎 "],
"en"    : ["嗯 恩 摁 "],
"er"    : ["二 而 兒 爾 耳 貳 邇 餌 珥 鉺 洱 佴 "],
"o"     : ["噢 哦 嚄 "],
"ou"    : ["區 謳 偶 歐 嘔 毆 鷗 嘔 藕 "]
}

VERSION = "alpha0.18 tone_test 1" # alpha = 內測; beta = 公測 | 0.** = 未全部完成; >0.** = 基礎功能完成; +1 = 重製或加入巨大功能 | test 次版測試次數 | 附加,如 gui_test 只更新gui
debug = False
tone = False
gui_beta = False
language = "t-chinese"
main_screen()()

```
### 返回[LIB臨時工作室：軟件產品](Software)
------------
#### [產品問題或建議反饋 請發送給我們的郵箱](mailto:feedback@libps.org)
------------

##### [繁體中文（台灣地區） - 切換您的語言](https://libps.github.io/index)
