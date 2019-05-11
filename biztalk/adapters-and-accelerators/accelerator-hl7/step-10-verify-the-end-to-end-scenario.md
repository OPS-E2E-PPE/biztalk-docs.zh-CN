---
title: 步骤 10:验证端到端方案 |Microsoft Docs
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
ms.openlocfilehash: 081f2e7f81c7ea293cac8717434a451d0d2ecd6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289054"
---
# <a name="step-10-verify-the-end-to-end-scenario"></a>步骤 10:验证端到端方案
在此步骤中，对于本教程中验证端到端方案。  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a>若要验证的端到端教程方案  
  
1. 单击**启动**，指向**程序**，指向**附件**，然后单击**命令提示符下**。  
  
2. 在命令提示符窗口中，转至 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\MLLP 实用工具Accelerator**，然后按**Enter**。  
  
   > [!NOTE]
   >  如果找不到 SDK 文件夹下的处的 MLLP 实用程序文件夹，可能不会安装 MLLP 测试工具。 打开控制面板，然后打开**添加或删除程序**。 选择**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后选择**更改**。 在 BTAHL7 安装程序向导中，选择**修改**。 展开**适配器**文件夹，以查看是否**MLLP 测试工具**已安装。 如果没有，请安装它。  
  
3. 在命令提示符窗口中，键入**mllpreceive/p 14000**，然后按**Enter**。 此运行 MLLP 侦听器应用程序侦听端口 14000 并指定默认 EB、 SB 和 CR 字符的 MLLP 消息，并显示在屏幕上收到任何消息。  
  
4. 通过单击启动其他的命令提示符**启动**，依次指向**程序**，指向**附件**，然后单击**命令提示符下**.  
  
5. 在第二个命令提示符窗口中，转至 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\MLLP 实用工具加速器**，然后按**Enter**。  
  
   > [!NOTE]
   >  以下步骤将消息发送。  
  
6. 在命令提示符窗口中，键入**mllpsend /SB 11 /EB 28 /CR 13 /f"\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\ 的快捷键端到端 Tutorial\ADT ^ A03.txt"**，其中\<*驱动器*\>是你安装的驱动器号。 按 **Enter**。  
  
7. 验证具有以下结果：  
  
   -   MLLP 侦听器应用程序应显示一条消息。 消息的第一行应具有以下值：  
  
       ```  
       MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
       ```  
  
   -   在出现一条消息\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_sendMsg_RX 的加速器。 此消息应处的 MLLP 侦听器应用程序所显示的消息相同。 验证消息的第一行具有相同的消息值，如下所示。 请注意，在下面的代码和 MSH5 MSH3 的值匹配 Tutorial_RXSystem 为指定的值：  
  
       ```  
       MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
       ```  
  
   -   两个消息将显示在\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_sendAck_ADT 的加速器。 其中一条消息是应用程序确认;另一个是提交确认。 应用程序确认应包含以下内容：  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
       MSA|AA|000001  
       ```  
  
   -   提交确认应包含以下内容：  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
       MSA|CA|000001  
       ```  
  
   > [!NOTE]
   >  如果未正确显示消息，请使用运行状况与活动跟踪 (HAT) 工具解决该错误。  
  
   祝贺你！ 已成功完成 BTAHL7 的端到端教程。  
  
## <a name="see-also"></a>请参阅  
 [端到端教程](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)