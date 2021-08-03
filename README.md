# 对话故事生成，创造自己的无限世界

如果可以，你最想穿越到哪部电影，小说里？

这次利用 paddlenlp 中提供的 GPT2 和 wechaty 库展开对话故事续写，与 AI 互动共同创造剧情

预先设置你想交互的世界场景，比如面对三体人的进攻，发挥你的脑洞输入你想到的任何动作或者剧情大纲，模型的续写保证让你赞(hei)不(ren)绝(wen)口(hao)

![问号](./imgs_q.png)

## 项目介绍

### 灵感来源

+ 1.《无限恐怖》 
+ 2.AI Dungeon

通过 AIDungeon 2 ，玩家将接触到一个完全自由的虚拟世界。整个游戏世界，都将围绕着玩家的输入展开与续写，可谓真正的 Everything is in my hands 
 
[体验地址 https://play.aidungeon.io/main/home](https://play.aidungeon.io/main/home)

本github代码中直接使用了paddlenlp提供的预训练模型`gpt-cpm-small-cn-distill `

在 AI Studio 中则是安装 `paddlenlp==2.0.0rc14` 然后引入的  `gpt2-base-cn` ，详情见AIStudio示例，生成效果还说的过去

注：在新版本的 paddlenlp 2.0.7 中已经找不到 gpt2-base-cn 预训练模型，本地运行还是推荐使用代码中引入的阿巴阿巴模型（ gpt-cpm-small-cn-distill ）400M，详情看代码注释

### 效果展示

* [AIStudio链接](https://aistudio.baidu.com/aistudio/projectdetail/2235967)

* [B站链接](https://aistudio.baidu.com/aistudio/projectdetail/2235967)

## 安装依赖

```sh
pip install --upgrade paddlepaddle -i https://mirror.baidu.com/pypi/simple
pip install --upgrade paddlehub -i https://mirror.baidu.com/pypi/simple
pip install paddlenlp=2.0.7
pip install sentencepiece=0.1.92
```

## 命令行交互测试对话系统

```sh
python world.py
```

## 引入wechaty

如果token是 padlocal 模式， 请先安装docker启动网关再进入下一步

```sh
# docker下载 wechaty/wechaty 镜像
docker pull wechaty/wechaty

# 确保gateway.sh中是自己的token， 服务器开启相关端口
sudo ./gateway.sh
```

然后访问此链接返回ip地址和端口，确认启动成功

https://api.chatie.io/v0/hosties/xxx你的token

启动 wechaty 监听聊天消息

请先把 main.py 中的 msg.talker().name 改成自己的微信昵称，不然向你发消息的人可能会收到奇怪的消息

```sh
# 安装wachaty
pip install wechaty

# 确认main.py中环境变量替换了自己的token，然后启动
python main.py
```

enjoy it ！


