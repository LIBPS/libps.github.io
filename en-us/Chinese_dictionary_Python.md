# Chinese dictionary(Py Addition)

#### Updated on July 21st 2023
#### （Apart from being inferior to the C++ version UI, everything else is quite impressive!————BQ）

```python
import os
def clear_screen():
    if os.name == 'nt':
        _ = os.system('cls')
    else:
        _ = os.system('clear')

def initialize_dictionary_file():
    text = """a
吖 阿 阿 啊 锕 腌 嗄
ai
哎 哀 锿 埃 挨 皑 癌 欸 矮 蔼 霭 艾 硙 砹 爱 嫒 瑷 叆 暧 隘 障
an
安 按 桉 氨 鹌 谙 盦 铵 俺 埯 唵 岸 按 胺 案 暗 黯
ang
肮 卬 昂 盎
ao
凹 熬 敖 嶅 嗷 獒 翱 鏖 拗 袄 奥
ba
丷 八 仈 巴 叭 朳 玐 吧 岜 扷 芭 夿 疤 柭 釟 蚆 粑 笆 捌 哵 羓 豝 鲃 叐 茇 妭 拔 癹 菝 軷 詙 跋 颰 魃 鼥 把 钯 鈀 靶 叭 把 伯 弝 坝 爸 杷 垻 罢 耙 跁 鲅 靶 罷 鮁 覇 矲 霸 壩 灞 欛 抜 鎺 鯐
bai
挀 掰 白 犤 百 伯 佰 陌 柏 栢 捭 絔 摆 擺 襬 庍 呗 拝 败 拜 敗 猈 稗 粺 薭 贁 韛 瓸 竡 粨 兡
ban
扳 肦 攽 班 般 颁 斑 斒 搬 頒 鳻 瘢 螌 褩 癍 辬 阪 岅 坂 板 版 昄 瓪 钣 粄 舨 鈑 蝂 魬 闆 办 半 伴 扮 拌 姅 绊 坢 怑 柈 秚 絆 湴 鉡 靽 辦 瓣 螁
bang
邦 帮 垹 梆 捠 浜 邫 幇 幚 縍 幫 鞤 绑 綁 榜 牓 膀 玤 挷 旁 蚌 棒 棓 傍 谤 蒡 搒 塝 稖 膀 蜯 榜 镑 磅 艕 謗 鎊
bao
勹 包 苞 孢 炮 枹 胞 剥 剝 笣 龅 煲 裦 褒 蕔 襃 闁 齙 窇 雹 薄 宝 饱 怉 鸨 保 宲 珤 葆 堡 堢 媬 寚 飽 飹 褓 駂 鳵 鴇 緥 賲 寳 寶 靌 勽 刨 报 抱 铇 豹 趵 蚫 菢 袌 报 鉋 鲍 骲 髱 暴 虣 鮑 曓 儤 瀑 爆 犦 曝 忁 鑤 佨 藵
bei
陂 卑 杯 柸 背 盃 桮 椑 揹 悲 鹎 碑 藣 鵯 北 鉳 贝 狈 孛 邶 貝 牬 昁 苝 备 郥 背 钡 被 倍 俻 狽 悖 梖 偝 偹 鄁 珼 琲 惫 軰 備 僃 棓 辈 焙 蓓 蛽 碚 愂 禙 犕 褙 誖 鞁 骳 鋇 輩 糒 憊 鞴 鐾 唄
ben
奔 泍 贲 犇 锛 錛 本 苯 奙 畚 翉 楍 夯 坌 倴 逩 桳 笨 捹 渀 撪
beng
伻 祊 奟 崩 绷 閍 絣 痭 嵭 嘣 綳 繃 甭 甮 埄 埲 菶 绷 琫 琣 鞛 迸 泵 蚌 逬 绷 揼 塴 甏 镚 蹦 鏰
bi
皀 屄 偪 逼 毴 楅 榌 豍 鵖 螕 鲾 鎞 鰏 荸 鼻 匕 比 朼 夶 吡 妣 沘 佊 疕 彼 毞 柀 秕 笔 粃 舭 俾 啚 筆 鄙 箄 聛 貏 币 必 毕 闭 庇 佖 诐 芘 邲 迊 坒 怭 怶 苾 妼 咇 泌 畀 畁 哔 荜 陛 贲 毖 柲 珌 疪 秘 铋 毙 狴 畢 袐 粊 笓 闭 閉 婢 庳 萆 萞 梐 敝 赑 堛 愊 愎 皕 禆 弼 弻 湢 詖 筚 賁 貱 蜌 裨 辟 閟 飶 鉍 滗 滭 嗶 彃 蓖 蓽 腷 睥 睤 痹 痺 煏 熚 碧 蔽 弊 鄪 獙 幣 綼 箅 箆 馝 髲 駜 襅 幤 潷 罼 獘 壁 廦 嬖 避 薜 篦 篳 縪 觱 鮅 蹕 髀 濞 斃 臂 奰 鏎 饆 鄨 璧 繴 襣 襞 鞸 魓 韠 躄 躃 驆 鷝 鐴 贔 朇 鷩 鼊 萙 蛯 嬶
bian
皀 屄 偪 逼 毴 楅 榌 豍 鵖 螕 鲾 鎞 鰏 荸 鼻 匕 比 朼 夶 吡 妣 沘 佊 疕 彼 毞 柀 秕 笔 粃 舭 俾 啚 筆 鄙 箄 聛 貏 币 必 毕 闭 庇 佖 诐 芘 邲 迊 坒 怭 怶 苾 妼 咇 泌 畀 畁 哔 荜 陛 贲 毖 柲 珌 疪 秘 铋 毙 狴 畢 袐 粊 笓 闭 閉 婢 庳 萆 萞 梐 敝 赑 堛 愊 愎 皕 禆 弼 弻 湢 詖 筚 賁 貱 蜌 裨 辟 閟 飶 鉍 滗 滭 嗶 彃 蓖 蓽 腷 睥 睤 痹 痺 煏 熚 碧 蔽 弊 鄪 獙 幣 綼 箅 箆 馝 髲 駜 襅 幤 潷 罼 獘 壁 廦 嬖 避 薜 篦 篳 縪 觱 鮅 蹕 髀 濞 斃 臂 奰 鏎 饆 鄨 璧 繴 襣 襞 鞸 魓 韠 躄 躃 驆 鷝 鐴 贔 朇 鷩 鼊 萙 蛯 嬶
biao
杓 标 飑 骉 髟 彪 淲 猋 脿 颮 滮 摽 骠 蔈 幖 墂 麃 標 熛 膘 镖 瘭 磦 飙 飚 儦 颷 謤 藨 瀌 爂 鏢 贆 臕 穮 镳 飆 飇 飈 飊 鑣 驫 表 婊 裱 諘 錶 褾 檦 俵 摽 鳔 鋲
bie
憋 瘪 蟞 鳖 癟 鱉 鼈 虌 龞 别 別 莂 蛂 徶 襒 蹩 瘪 别 彆
bin
邠 玢 宾 彬 梹 椕 傧 斌 滨 缤 賓 賔 豩 槟 瑸 镔 儐 濒 頻 豳 濱 濵 虨 璸 檳 瀕 霦 繽 蠙 鑌 顮 摈 殡 膑 髩 鬂 擯 殯 臏 髌 鬓 髕 鬢
bing
冫 仌 氷 并 冰 兵 屏 栟 掤 槟 丙 邴 陃 苪 怲 抦 秉 昞 昺 炳 柄 屏 饼 绠 眪 蛃 偋 寎 棅 鈵 禀 稟 鉼 餅 餠 鞞 并 幷 並 併 庰 倂 栤 竝 病 窉 傡 摒 誁 鮩 靐 垪 鞆
bo
癶 癷 波 拨 玻 饽 钵 盋 砵 哱 剥 般 趵 缽 紴 袰 菠 啵 溊 碆 鉢 鲅 僠 蕃 嶓 播 撥 餑 礡 蹳 驋 鱍 仢 伯 驳 孛 肑 瓝 泊 狛 帛 郣 勃 侼 胉 柏 袯 瓟 秡 钹 铂 浡 挬 亳 萡 淿 脖 袹 舶 鹁 渤 葧 博 猼 馎 愽 搏 鈸 鉑 鲌 魄 馛 駁 艊 箔 牔 煿 膊 僰 镈 踣 鋍 馞 駮 鮊 薄 謈 襏 簙 餺 鵓 鎛 嚗 懪 髆 髉 糪 襮 欂 礴 鑮 癷 跛 簸 柏 薄 孹 檗 擘 簸 譒 蘗 畓 蔔
bu
逋 庯 峬 钸 晡 鈽 誧 餔 錻 不 鳪 轐 醭 卜 卟 补 哺 捕 堡 補 鵏 鸔 佈 步 怖 咘 钚 柨 悑 部 勏 捗 埔 埗 荹 埠 瓿 鈈 蔀 廍 踄 郶 餢 篰 簿 巭
e
额 呃 饿 讹 恶 鹅 谔 噩 厄 颚
en
嗯 恩 摁
er
二 而 儿 尔 耳 贰 迩 饵 珥 铒 洱 佴
o
噢 哦 嚄
ou
区 讴 偶 欧 呕 殴 鸥 呕 藕
"""
    text_tone = """"""
    if os.path.exists(path):
    #   with open(path, "w", encoding="utf-8") as f:
    #       f.write(text)
        pass
    else:
        with open(path, "x", encoding="utf-8") as f:
            f.write(text)
    
    if os.path.exists(path_tone):
    #   with open(path, "w", encoding="utf-8") as f:
    #       f.write(text)
        pass
    else:
        with open(path_tone, "x", encoding="utf-8") as f:
            f.write(text_tone)

def main_screen():
    clear_screen()
    if debug:
        print(f"debug = True\n")
    print(f"""欢迎来到字典程序(py addition)(By:MiXiaozai Studio)

请选择您的模式(输入前面的序号)
  s.查字模式
  d.字典附件
  f.更新日志
  g.制作人员
  h.字典程序设置
  j.指令帮助

当前版本号:{version}
请您输入模式:""",end="")
    inp = input().lower()
    if inp in ["s", "d", "f", "g", "h"]:# j
        mode = {"s": search, "d": more, "f": log, "g": dev, "h": settings}
        return mode[inp]
    elif inp.startswith("/") or inp == "j":
        if inp == "/debug":
            return F3
        elif inp.startswith("/help") or inp == "j":
            try:
                input(help_dir[inp[6:]])
            except:
                try:
                    if inp[5] == " ":
                        input("你要查找的指令未找到")
                    else:
                        input("你在输入一个指令吗？如果是，请使用正确的指令格式")
                        main_screen()()
                except:
                    for i in help_dir:
                        print(help_dir[i])
                    input()
            main_screen()()
        elif inp == "/back":
            clear_screen()
            quit()
        else:
            input("你在输入一个指令吗？如果是，请使用正确的指令格式")
            main_screen()()
    else:
        input("你的输入有误")
        main_screen()()

def search():
    clear_screen()
    global tone

    with open(path,"r", encoding="utf-8") as f:
        text = f.readlines()
    while True:
        if debug:
            print(f"tone = {tone}\n")
        inp = input("请输入拼音或/help:\n").lower()

        if inp.startswith("/"):
            if inp[:4] == "/all":
                cnt = 0
                from math import ceil
                for i in range(1, len(text), 2):
                    print("".join(map(lambda _: text[i - 1][_], range(len(text[i - 1]) - 1))), end = "\t")
                    print(text[i], end = "")
                    cnt += ceil(len(text[i]) / 2)
                input(f"\n\n共收录{cnt}字\n")
            elif inp[:5] == "/help":
                try:
                    if inp[5] == " ":
                        search_help(inp)
                    else:
                        input("你在输入一个指令吗？如果是，请使用正确的指令格式\n")
                except:
                    search_help(inp)
            elif inp[:5] == "/back":
                main_screen()()
            elif inp[:5] == "/tone":
                clear_screen()
                if tone:
                    input("声调关")
                else:
                    input("声调开")
                #tone = bool(int(tone) - 1)
            else:
                input("你在输入一个指令吗？如果是，请使用正确的指令格式\n")
        
        for i in range(0, len(text), 2):
            if inp + "\n" == text[i]:
                input(text[i + 1])
        clear_screen()      
def search_help(inp:str):
    try:
        input(help_dir[inp[6:]])
    except:
        if len(inp) > 6:
            input("你要查找的指令未找到")
        else:
            for i in help_dir:
                print(help_dir[i])
            input()

def more():
    clear_screen()
    inp = input("""(1)\t*.md -> *.html\t(注:需要markdown库;此功能未完成)
(2)\tnltk集合\t(注:需要nltk库;此功能未完成)
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
        input("你没有markdown库\n") 
        more()   
    input("此功能未完成")
    more()
def more__nltk():
    clear_screen()
    try:
        import nltk
    except ModuleNotFoundError:
        input("你没有nltk库\n")
        more()
    try:
        from nltk.corpus import words
    except:
        nltk.download('words')
    print(words.words(language))
    input("此功能未完成")
    more()

def log():
    clear_screen()
    input("""[2023/6/13 19:37] 实现了更新日志,作者名单,第一条指令(/op)(目前没用)
[2023/6/14 16:05] 实现了查字模式指令(/all)
[2023/6/15 18:19] 查字系统完成,无声调与C++版本同步更新;有声调版本基于http://xh.5156edu.com/pinyi.html更新
[2023/6/17 10:53] 实现指令(/debug)和(/tone)删除指令(/op)
[2023/7/12 15:58] 与C++版本同步更新
[2023/7/19 14:52] 更新字典附件
[2023/7/20 19:45] 加强查字模式指令(/help)
[2023/7/21 10:48] 加强主页指令(/help)
""")
    main_screen()()
def dev():
    clear_screen()
    input("""主要开发:Lucas
    
原版制作:BQ
    """)
    main_screen()()
def settings():
    clear_screen()
    print(f"{path} 文件(查字系统的字库,删除后重新安装,更改后不会覆盖)内容:")
    with open(path, "r", encoding="utf-8") as f:
        for line in f:
            print(line, end="")
    print("\n")
    print(f"{path_tone} 文件(拼音查字系统的字库,删除后重新安装,更改后不会覆盖)内容:")
    with open(path_tone, "r", encoding="utf-8") as f:
        for line in f:
            print(line, end="")
    input("\n\n目前没有可更改选项\n")
    main_screen()()
def F3():
    global debug
    if debug:
        input("开发者信息关")
    else:
        input("开发者信息开")
    debug = bool(int(debug) - 1)
    main_screen()()

global path, path_tone, version, debug, tone, help_dir

help_dir = {"all" : "/all\t输出所有收录字",
            "back": "/back\t退出",
            "help": "/help\t显示此列表,单个空格后加指令(不加\"/\")可以精确查找",
            "tone": "/tone\t在查字模式输入切换声调模式(nǐ hǎo => ni3 ha3o)",
            "debug":"/debug\t在主页输入切换更多信息显示"}
path = "D:\py_addition_data.txt"
path_tone = "D:\py_addition_data_tone.txt"
version = "alpha0.16"
debug = False
tone = False
language = "chinese"

initialize_dictionary_file()

main_screen()()


#https://www.luogu.com.cn/chat?uid=767126
```
### [Back to LIB Provisional Studio:Software](https://libps.github.io/en-us/Software) 
##### [American English (United States) - Switch Your Language](https://libps.github.io/index)
