# 创造自己的无限流冒险世界

![image](https://github.com/henry-ren/images/blob/main/1.jpeg)

预先设置你想交互的世界场景，比如面对三体人的进攻，而你恰巧在逃亡主义的飞船上，你会选择怎么做

发挥你的脑洞，输入你想到的任何动作，机器人会尝试将剧情延续下去，虽然它并不完美，但一切皆有可能！

灵感来源 

+ 1.《无线恐怖》 无限流小说的开山鼻祖，包罗万象的世界观，包含无限的可能性 
+ 2.AI Dungeon

直接使用了paddlenlp引入的预训练模型

本机快速测试可以使用 阿巴阿巴胡言乱语模型 gpt-cpm-small-cn-distill

在 ai studio 中可以安装 paddlenlp==2.0.0rc14 然后引入 gpt2-base-cn ，能得到不错的效果

## 安装依赖

```sh
pip install --upgrade paddlepaddle -i https://mirror.baidu.com/pypi/simple
pip install --upgrade paddlehub -i https://mirror.baidu.com/pypi/simple
pip install paddlenlp=2.0.7
pip install sentencepiece=0.1.92
```

注： 在新版本的 paddlenlp 2.0.7 中已经找不到 gpt2-base-cn 预训练模型， 所以使用较小的 gpt-cpm-small-cn-distill （400M）

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

请先把 main.py 中的 msg.talker().name 改成自己的用户名，不然向你发消息的人会收到奇怪的阿巴阿巴阿巴

```sh
# 安装wachaty
pip install wechaty

# 确认main.py中环境变量替换了自己的token，然后启动
python main.py
```

enjoy it ！


