---
title: 步骤 3： 配置参与方和业务配置文件在 Organization1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 849e5146-a82a-41f2-bb96-089841b2444d
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5427ca12ff031bb7fa045a78709f97fdbb49fdb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023475"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a>步骤 3： 为你的组织配置参与方和业务配置文件
![第 3 部分，共 9 步](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")  
  
 在此步骤中，你将为组织配置参与方和业务配置文件，以便接收来自贸易合作伙伴的 850 消息，并返回 997 确认消息。  
  
## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a>为组织配置参与方和业务配置文件  
  
1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过单击管理控制台**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。 右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  
  
3. 在中**参与方属性**对话框框中，输入**OrderSystem**中**名称**字段。  
  
4. 选择**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框。 通过选中复选框来指定的参与方 (在这种情况下， **OrderSystem**) 还托管 BizTalk Server。  
  
5. 单击“确定” 。  
  
6. 右键单击参与方名称，指向**新建**，然后单击**业务配置文件**。  
  
7. 在中**配置文件属性**对话框中，在**常规**页上，输入`OrderSystem_Profile`中**名称**文本框。  
  
   > [!NOTE]
   >  一个配置文件时创建的参与方，名为*PartyName*（_p） 自动创建。 你可以使用此配置文件，不必创建新的配置文件。 若要重命名配置文件，请右键单击该配置文件，然后选择**属性**。 在中**常规**页上，指定配置文件的名称。  
  
8. 单击“确定” 。  
  
## <a name="next-steps"></a>后续步骤  
 为你的合作伙伴组织配置参与方和业务配置文件 (**Fabrikam**)，如中所述[步骤 4： 为您的贸易合作伙伴配置参与方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)