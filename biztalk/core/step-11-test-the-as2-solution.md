---
title: 步骤 11:测试 AS2 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 184ed8ee-6778-4bb9-b265-a94a1fed03cb
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad7b87895503308cf72858a7bc3c76d716b4b4a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392784"
---
# <a name="step-11-test-the-as2-solution"></a>步骤 11:测试 AS2 解决方案
![步骤 11 11](../core/media/tut-step11-of-11.gif "Tut_Step11_of_11")  
  
 在此步骤验证本教程的结果。  
  
 需要生成 Sender.exe 文件，用来发送 EDI 消息到 Receive_AS2 接收位置 （通过 Contoso 虚拟目录）。 Sender.exe 返回异步 MDN 消息。 消息文件是 X12_00401_864.edi，位于[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial 文件夹。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-test-the-solution-with-an-asynchronous-edi-message"></a>若要使用异步 EDI 消息测试解决方案  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开中的 Sender.csproj 项目[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender 文件夹。 右键单击 Sender 项目，然后单击**属性**。 单击**签名**左侧控制台中。 絋粄**为程序集签名**是选择，并将强名称密钥文件设置为**Sender.snk**。 请确保**仅延迟签名**清除。  
  
2. 生成项目。  
  
3. 打开命令提示符并导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Sender\bin\debug。 Enter `Sender.exe`，然后按**Enter**。 验证看到一条消息，该值指示已成功发送的 AS2 消息，然后关闭命令提示符。  
  
   > [!NOTE]
   >  运行 Sender.exe 构建包含下列 EDI 测试交换的 AS2 消息：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\X12_00401_864.edi. 生成 AS2 消息之后, 它将其发布到 Contoso 虚拟目录，后者使用 BTSHttpReceive.dll 将消息路由到接收位置。  
  
4. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_MDNToFabrikam 文件夹。 验证是否有\<GUID\>.msg 文件格式的文件夹中。 在记事本中，打开文件，并验证该消息是一个 MDN 的 AS2-From 设置为 Contoso 和 AS2-To 设置为 Fabrikam。  
  
5. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso 文件夹。 验证是否有\<GUID\>文件夹中的.xml 文件。 双击该文件，并验证该消息的 ST01 字段设置为 864。  
  
6. 导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_997ToFabrikam 文件夹。 验证是否有\<GUID\>.msg 文件格式的文件夹中。 在记事本中，打开文件并验证消息与 AS2 标头 997 消息 （带有 997 的 ST1) 具有 EDI 负载上。 验证 AS2-从是 Contoso 和 AS2-To 是 Fabrikam。 验证此 ISA6 （发送方标识符） 设置为 1234567 (Contoso) 和 ISA8 （接收方标识符） 设置为 7654321 (Fabrikam)。  
  
7. 若要查看 AS2 和 EDI 状态报告，请转到**组中心**BizTalk Server 管理控制台中的页上，滚动到底部的页上，并单击其中一个状态报告链接。 有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
## <a name="next-steps"></a>后续步骤  
 已完成 AS2 教程。  
  
## <a name="see-also"></a>请参阅  
 [教程 3：AS2 教程](../core/tutorial-3-as2-tutorial.md)   
 [步骤 1：AS2 教程的准备工作](../core/step-1-prepare-for-the-as2-tutorial.md)