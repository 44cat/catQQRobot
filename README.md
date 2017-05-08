# catQQRobot

* smart QQRobot
* 我现在设置的就是 你问“在吗”，然后从我给定的答案里随机回复
 
## 简单代码如下

from qqbot import QQBotSlot as qqbotslot, RunBot

import random

@qqbotslot

def onQQMessage(bot, group, member, content):

      if content == '在吗':
          return_content = ['额，我在坐公交','我在洗澡，等下回你','在上课，等下再说哈','觅食中，稍后回复，嘻嘻']
          ret = random.choice(return_content)
          bot.SendTo(group,ret)
       elif content == 'stop':
          bot.SendTo(group, 'QQ机器人已关闭')
          bot.Stop()
           
if \_\_name__ == '\_\_main__':

     RunBot()

