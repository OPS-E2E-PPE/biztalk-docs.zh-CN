---
title: "步骤 9： 验证零碎的入站的批处理方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ba61866-2e1b-49e2-be57-ef281407d0a5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47d5ec8ffa7a7875af7073e60d6578149d532a7a
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="step-9-verify-the-fragmented-inbound-batch-scenario"></a>步骤 9： 验证零碎的入站的批处理方案
在此步骤中，你可以验证分片入站批处理方案。  
  
 正在验证方案涉及使用以下工具：  
  
-   **MllpSend 工具**，从命令行中用于将批处理消息发送到接收端口。  
  
-   **MllpReceive 工具**，从命令行中用于验证来自发送端口 （作为包含批处理中） 的单个消息的接收。 此实例 MllpReceive 工具充当模拟的业务线应用程序。 在收到的消息，它还生成确认回[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]集成引擎。  
  
-   MllpReceive 工具，它用于验证接收的从发送端口的确认第二个实例。  
  
### <a name="to-test-the-fragmented-inbound-batch-scenario"></a>若要测试分片入站批处理方案  
  
1.  单击**启动**，指向**所有程序**，指向**附件**，然后单击**命令提示符**。  
  
2.  在命令提示符下，将移到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用工具**。  
  
3.  在命令提示符处，键入**mllpreceive/p 41000 /sb 11 /eb 28 /cr 13 /hl7ack"\<*驱动器*\>: files\microsoft BizTalk\<版本\>快捷键HL7\Samples\Sample 应用程序接受 ACK.txt**，然后按**Enter**。 命令提示符窗口进入等待状态，直到你执行步骤 5 和系统接收输入。  
  
    > [!NOTE]
    >  步骤 3 中的命令运行侦听端口 41000 MLLP 侦听器应用程序。 此端口是与发送端口将消息传送相关联 (在创建[步骤 5： 创建到传递消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md))。 MllpReceive 工具充当的业务线应用程序接收的消息，并将确认 (ACK) 发送回 BTAHL7 （为包含在示例应用程序接受 ACK.txt 的示例文件）。 该工具显示在命令提示符窗口中返回到它的任何消息。 步骤 3 中的命令指定 MLLP 消息的默认 EB、 SB 和 CR 字符。  
  
4.  重复步骤 1 和 2，打开另一个命令提示符窗口并浏览至 MLLP Utilities 目录。 在命令提示符处，键入**mllpreceive/p 41002**，然后按**Enter**。 命令提示符窗口进入等待状态，直到你执行步骤 5 和系统接收输出。  
  
    > [!NOTE]
    >  步骤 4 中的命令运行侦听端口 41002 MLLP 侦听器应用程序。 此端口是与将确认传递回批处理消息源发送端口相关联 (在创建[步骤 6： 创建到传递确认发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md))。 MllpReceive 工具充当的业务线应用程序发送原始的批处理。 该工具会显示任何确认返回到它在命令提示符窗口中。 步骤 4 中的命令指定 MLLP 消息的默认 EB、 SB 和 CR 字符。  
  
5.  重复步骤 1 和 2，打开另一个命令提示符窗口并浏览至 MLLP Utilities 目录。 在命令提示符处，键入**mllpsend /twoway /sb 11 /eb 28 /cr 13 /f"\<*驱动器*\>: \Batching Tutorial\Instances\FragmentedInboundBatch.txt"/ p 21000**，其中\<*驱动器*\>是你安装的驱动器号，，然后按**Enter**。  
  
    > [!NOTE]
    >  步骤 5 中的命令模拟发送到接收端口原始批处理消息。 控制台应显示"已发送消息： 1"，指示 MllpSend 工具发送一批消息。 如果它不会显示"已发送消息： 1"，检查事件查看器中。 验证在步骤 5 中输入命令的文本，然后解决的配置发送和接收端口和的状态[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 BTAHL7。  
  
### <a name="to-verify-the-results-of-the-fragmented-inbound-batch-tutorial"></a>若要验证的分片入站批处理教程结果  
  
1.  验证一小段延迟后，对端口 41000 上的消息的侦听 MllpReceive 工具显示的批次中分片和发送到 Tutorial_BatchSource 方的单个消息的内容。 两个消息的内容应如下所示：  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT^A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT^A03|000002|Tutorial_BatchSource|MESA_IS|  
  
2.  验证一小段延迟后，侦听端口 41002 上确认 MllpReceive 工具将显示两个确认从 BTAHL7 集成引擎返回到批处理的源的内容。 两个确认的内容应如下所示：  
  
    |MSH.9|MSH.3|MSH.5|MSA.2|MSA.1|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK^A03^ACK|MESA_IS|Tutorial_BatchSource|000001|AA|  
    |ACK^A03^ACK|MESA_IS|Tutorial_BatchSource|000002|AA|  
  
## <a name="see-also"></a>另请参阅  
 [第 2 部分： 中的批处理 / 批处理出方案](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [第 3 部分：Create-Batch 方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)