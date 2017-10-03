---
title: "步骤 11： 测试 AS2 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 184ed8ee-6778-4bb9-b265-a94a1fed03cb
caps.latest.revision: "34"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 490833859717ec37e0cb53ae89497aa361adda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-11-test-the-as2-solution"></a>步骤 11： 测试 AS2 解决方案
![步骤 11 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")  
  
 在此步骤中，你将验证此教程的结果。  
  
 你需要生成 Sender.exe 文件，以用于将 EDI 消息发送到 Receive_AS2 接收位置（通过 Contoso 虚拟目录）。 Sender.exe 返回一个异步 MDN 消息。 消息文件是位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\AS2 Tutorial 文件夹中的 X12_00401_864.edi。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-test-the-solution-with-an-asynchronous-edi-message"></a>使用异步 EDI 消息测试解决方案  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹中的 Sender.csproj 项目。 右键单击 Sender 项目，然后单击**属性**。 单击**签名**在左侧的控制台。 确保**对程序集签名**是选择，并将强名称密钥文件设置为**Sender.snk**。 请确保**仅延迟签名**处于未选中状态。  
  
2.  生成此项目。  
  
3.  打开命令提示符，导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug。 Enter `Sender.exe`，然后按**Enter**。 验证你已看到一条消息，指出 AS2 消息已成功发送，然后关闭命令提示符窗口。  
  
    > [!NOTE]
    >  运行包含以下 AS2 消息的 Sender.exe 生成 EDI 测试交换： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\X12_00401_864.edi。 生成 AS2 消息后，它将把该消息发布到 Contoso 虚拟目录，该虚拟目录使用 BTSHttpReceive.dll 将消息路由到接收位置。  
  
4.  导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_MDNToFabrikam 文件夹。 验证是否有\<GUID > 文件夹中的消息文件。 在记事本中打开该文件，验证消息是一个 MDN，且 AS2-From 设置为 Contoso，AS2-To 设置为 Fabrikam。  
  
5.  导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_EDIXMLToContoso 文件夹。 验证是否有\<GUID > 文件夹中的.xml 文件。 双击该文件，然后验证消息的 ST01 字段设置为 864。  
  
6.  导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_997ToFabrikam 文件夹。 验证是否有\<GUID > 文件夹中的消息文件。 在记事本中打开该文件，验证消息是一个 997 消息（带有 997 的 ST1）且具有 EDI 负载上的 AS2 标头。 验证 AS2-From 是 Contoso，AS2-To 是 Fabrikam。 验证 ISA6（发送方标识符）设置为 1234567 (Contoso) 且 ISA8（接收方标识符）设置为 7654321 (Fabrikam)。  
  
7.  若要查看的 EDI 和 AS2 状态报告，请转到**组中心数据库**页在 BizTalk Server 管理控制台中，滚动到该页的底部，单击一个状态报表链接。 有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
## <a name="next-steps"></a>后续步骤  
 你已完成 AS2 教程。  
  
## <a name="see-also"></a>另请参阅  
 [教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)   
 [步骤 1： 准备 AS2 教程](../core/step-1-prepare-for-the-as2-tutorial.md)