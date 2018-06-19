---
title: 步骤 10： 验证端到端方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, verifying solution
ms.assetid: 24b74ba6-e303-4ab1-8a93-25a430e4894d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d38f137625554bd689477964e3a969142eca0658
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25961587"
---
# <a name="step-10-verify-the-end-to-end-scenario"></a>步骤 10： 验证端到端方案
在此步骤中，你可以出于本教程验证端到端方案。  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a>若要验证的端到端教程方案  
  
1.  单击**启动**，指向**程序**，指向**附件**，然后单击**命令提示符**。  
  
2.  在命令提示符窗口中，将移到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用工具**，然后按**Enter**。  
  
    > [!NOTE]
    >  如果找不到 SDK 文件夹下的 MLLP Utilities 文件夹，可能未安装 MLLP 测试工具。 打开控制面板，然后打开**添加或删除程序**。 选择**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后选择**更改**。 在 BTAHL7 安装向导中，选择**修改**。 展开**适配器**文件夹以查看是否**MLLP 测试工具**已安装。 如果没有，请安装它。  
  
3.  在命令提示符窗口中，键入**mllpreceive/p 14000**，然后按**Enter**。 这运行 MLLP 侦听器应用程序侦听端口 14000 并指定 MLLP 消息中，默认 EB、 SB 和 CR 字符，并显示到屏幕接收任何消息。  
  
4.  通过单击启动其他的命令提示符**启动**，指向**程序**，指向**附件**，然后单击**命令提示符**.  
  
5.  在第二个命令提示符窗口中，将移到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\MLLP 实用工具快捷键**，然后按**Enter**。  
  
    > [!NOTE]
    >  以下步骤将消息发送。  
  
6.  在命令提示符窗口中，键入**mllpsend /SB 11 /EB 28 /CR 13 /f"\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键端到端 Tutorial\ADT ^ A03.txt"**，其中\<*驱动器*\>是你安装驱动器号。 按 **Enter**。  
  
7.  请验证您具有以下结果：  
  
    -   MLLP 侦听器应用程序应显示一条消息。 消息的第一行应具有以下值：  
  
        ```  
        MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
        ```  
  
    -   消息将出现在\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_sendMsg_RX 快捷键。 此消息应显示 MLLP 侦听器应用程序的消息相同。 验证消息的第一行，如下所示具有相同的消息值。 请注意 MSH3 和 MSH5 下面的代码中的值与你为 Tutorial_RXSystem 指定的值匹配：  
  
        ```  
        MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
        ```  
  
    -   两个消息将显示在\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_sendAck_ADT 快捷键。 这些消息之一是应用程序确认;另一种是一个提交确认。 该应用程序确认应具有以下内容：  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
        MSA|AA|000001  
        ```  
  
    -   提交确认应具有以下内容：  
  
        ```  
        MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
        MSA|CA|000001  
        ```  
  
    > [!NOTE]
    >  如果未正确显示消息，使用运行状况和活动跟踪 (HAT) 工具解决此错误。  
  
 恭喜！ 你已成功完成 BTAHL7 端到端教程。  
  
## <a name="see-also"></a>另请参阅  
 [端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)