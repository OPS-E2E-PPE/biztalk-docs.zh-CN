---
title: 步骤 5：配置接收端口和接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4f4976c585caf858c27680b156ec3d01b09d439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244351"
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a>步骤 5：配置接收端口和接收位置
![步骤 5 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 在此步骤中配置接收端口和接收位置接收 850 消息的 Fabrikam 参与方设置的文件夹中。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a>若要配置接收端口和接收位置以接收 850 消息  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，然后**BizTalk应用程序 1**。 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
2. 在接收端口属性对话框中，在**名称**字段中，输入`ReceiveEDI_fromTHEM_A`。  
  
3. 单击**接收位置**在控制台树中，然后单击**新建**右侧窗格中。  
  
4. 在中**接收位置属性**对话框中**名称**字段中，输入`fromTHEM_4010_850`。  
  
5. 有关**类型**，选择**文件**，然后单击**配置**。  
  
   > [!NOTE]
   >  由于测试消息是平面文件传送到文件夹，接收位置的传输类型为 FILE。  
  
6. 在中**FILE 传输属性**对话框中，单击**浏览**按钮旁边**接收文件夹**字段。 在中**浏览文件夹**对话框中，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM，然后单击**确定**。  
  
7. 在中**FILE 传输属性**对话框中，更改**文件掩码**到 **\*.txt**然后单击**确定**。  
  
   > [!NOTE]
   >  由于输入的测试消息是一个文本文件，SamplePO.txt 文件掩码设置为 *.txt。  
  
8. 在中**接收位置属性**对话框中**接收管道**字段中，选择**EdiReceive**。  
  
   > [!NOTE]
   >  接收管道用于接收 EDI 交换，除通过 AS2 传输传递的之外是 EdiReceive 管道。 (AS2EdiReceive 接收管道用于接收通过 AS2 传输 EDI 交换。)  
  
   > [!NOTE]
   >  如果 EdiReceive 接收管道的下拉列表中未列出，应用程序可能不具有对 BizTalk EDI 应用程序的引用。 若要添加引用，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
9. 单击**确定**，然后单击**确定**试。  
  
   > [!NOTE]
   >  此外应为具有 BizTalk 服务登录权限的帐户授予与 fromTHEM_4010_850 接收位置关联的接收文件夹的完全访问权限 ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM)。 如果没有，请尝试启用接收位置时，将收到错误。 若要更改接收文件夹的访问权限，请转到在中的安全选项卡**属性**对话框中，在 Windows 资源管理器中该文件夹。  
  
10. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**接收位置**，右键单击**fromTHEM_4010_850**，然后单击**启用**。  
  
## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**toOrderSystem**) 以将 850 消息发送到 OrderSystem，如中所述[步骤 6:配置发送端口以将数据发送到你的组织](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置接收 EDI 消息和确认的端口](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)