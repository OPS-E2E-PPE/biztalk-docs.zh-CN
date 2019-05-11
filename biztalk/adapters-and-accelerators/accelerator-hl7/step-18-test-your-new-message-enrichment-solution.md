---
title: 步骤 18:测试新消息充实解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, testing solution
ms.assetid: 233fbf79-0ab1-4064-b828-6bbbb56cbec2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8f57aeb039d2ff4e33f2bfcf14a2d4cf2257f27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288740"
---
# <a name="step-18-test-your-new-message-enrichment-solution"></a>步骤 18:测试新消息充实解决方案
通过使用 WSClient 应用程序将消息发送到在此步骤中，测试您的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]并查看按预期方式 MLLPReceive 应用程序是否接收 HL7 格式的消息。  
  
### <a name="to-test-your-solution"></a>若要测试你的解决方案  
  
1.  打开命令提示符。  
  
    > [!NOTE]
    >  步骤 2 要求您已安装 MLLP 测试工具使用的自定义安装过程。 如果您的计算机不存在目录包含 MllpReceive.exe 和 MllpSend.exe \MLLP 实用程序通过执行自定义安装中安装。 有关信息，请参阅[执行自定义安装](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)。  
  
2.  在命令提示符处，键入**cd \<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\MLLP 实用工具 Accelerator** (其中\<*驱动器*\>是你安装的驱动器号)，然后按**Enter**。  
  
3.  在命令提示符处，键入**mllpreceive/p 11000 /eb 11 /sb 28 /cr 13**，然后按**Enter**。 此运行 MLLP 侦听器应用程序侦听端口 11000 并指定默认 EB、 SB 和 CR 字符的 MLLP 消息，并显示在屏幕上收到任何消息。  
  
4.  打开第二个命令提示符。  
  
5.  在命令提示符处，键入**cd \<*驱动器*\>: \Tutorial\WSClient\bin\Debug**，然后按**Enter**。  
  
6.  在命令提示符处，键入**wsclient john henry smith 123456789**，然后按**Enter**。 这将一条消息发送到包含示例社会安全号码的 123456789 和 John Henry Smith 患者名称的示例消息的 Web 服务。  
  
7.  片刻时间 MLLPReceive 应用程序显示传入 MLLP 消息。 该消息应类似于下面所示：  
  
    ```  
    MSH|^~\&|TestTrailing^Delimiters|srcFac^srcFacUid|dstApp^dstAppUid|dstFac^dstFacUid|200307092343|sec|ADT^A04|msgid2134|P|2.2PID|||123456789||smith^john  
    ```  
  
     如果在几分钟后未收到响应，应检查应用程序事件日志的任何错误，并开始进行故障排除。  
  
## <a name="see-also"></a>请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)