---
title: 步骤 4： 配置参与方和业务配置文件贸易 Partner1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db50d0f6-e838-4e92-8548-a63a2c445d55
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa53034af1a07ca55574e2e37eecb7c0875f8a2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989678"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a>步骤 4： 为贸易合作伙伴配置参与方和业务配置文件
![步骤 4 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 在此步骤中，你将为你的贸易合作伙伴 Fabrikam 配置一个参与方和业务配置文件，以便向组织发送 850 消息，并接收返回的 997 确认消息。  
  
## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a>为你的贸易合作伙伴配置参与方和业务配置文件  
  
1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。 右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  
  
3. 在中**参与方属性**对话框框中，输入**Fabrikam**中**名称**字段。  
  
4. 清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框。 通过清除复选框指定的参与方 (在这种情况下， **Fabrikam**) 不托管 BizTalk Server。  
  
5. 单击“确定” 。  
  
6. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  
  
7. 在中**配置文件属性**对话框中，在**常规**页上，输入`Fabrikam_Profile`中**名称**文本框。  
  
   > [!NOTE]
   >  一个配置文件时创建的参与方，名为*PartyName*（_p） 自动创建。 你可以使用此配置文件，不必创建新的配置文件。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  
  
8. 单击“确定” 。  
  
## <a name="next-steps"></a>后续步骤  
 配置接收位置 (**fromTHEM_4010_850**) 以从 Fabrikam 接收 850 消息中所述[步骤 5： 配置接收端口和接收位置](../core/step-5-configure-a-receive-port-and-receive-location.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)