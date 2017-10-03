---
title: "步骤 5： 配置接收端口和接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8ec436657aefaceb71207d37808936aa6eaa1a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a>步骤 5： 配置接收端口和接收位置
![步骤 5 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 在此步骤中，您将为接收 850 消息配置接收端口和接收位置，该消息位于为 Fabrikam 参与方设置的文件夹中。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a>配置接收端口和接收位置以接收 850 消息  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，，然后**BizTalk应用程序 1**。 右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
2.  在接收端口属性对话框中，在**名称**字段中，输入`ReceiveEDI_fromTHEM_A`。  
  
3.  单击**接收位置**在控制台树中，然后单击**新建**右侧窗格中。  
  
4.  在**接收位置属性**对话框中，在**名称**字段中，输入`fromTHEM_4010_850`。  
  
5.  有关**类型**，选择**文件**，然后单击**配置**。  
  
    > [!NOTE]
    >  由于测试消息是传送到文件夹中的平面文件，因而接收位置的传输类型为 FILE。  
  
6.  在**文件传输属性**对话框中，单击**浏览**按钮旁边**接收文件夹**字段。 在**浏览文件夹**对话框中，移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员 Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM，，然后单击**确定**。  
  
7.  在**文件传输属性**对话框中，更改**文件掩码**到 **\*.txt**单击**确定**。  
  
    > [!NOTE]
    >  由于输入测试消息为文本文件 SamplePO.txt，因此文件掩码应设为 *.txt。  
  
8.  在**接收位置属性**对话框中，在**接收管道**字段中，选择**EdiReceive**。  
  
    > [!NOTE]
    >  用于接收 EDI 交换的接收管道除通过 AS2 传输类型传递的之外其他均为 EdiReceive 管道。 （AS2EdiReceive 接收管道用于接收通过 AS2 传输类型发送的 EDI 交换。）  
  
    > [!NOTE]
    >  如果 EdiReceive 没有在接收管道的下拉列表中列出，您的应用程序可能就没有对 BizTalk EDI 应用程序的引用。 若要添加的引用，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
9. 单击**确定**，然后单击**确定**试。  
  
    > [!NOTE]
    >  具有 BizTalk 服务登录权限的帐户应该也享有对与 fromTHEM_4010_850 接收位置 ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM) 相关联的接收文件夹的完全访问权限。 否则，在尝试启用接收位置时将出现错误。 若要更改的接收文件夹的访问权限，请转到中的安全选项卡**属性**对话框中，在 Windows 资源管理器中该文件夹。  
  
10. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**接收位置**，右键单击**fromTHEM_4010_850**，然后单击**启用**。  
  
## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**toOrderSystem**) 中所述将 850 消息发送到 OrderSystem，[步骤 6： 配置发送端口将数据发送到你的组织](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置端口以接收 EDI 消息，确认](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)