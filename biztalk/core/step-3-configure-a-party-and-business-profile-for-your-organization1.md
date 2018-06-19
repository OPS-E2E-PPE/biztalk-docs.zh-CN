---
title: 步骤 3： 为你 Organization1 配置方和业务配置文件 |Microsoft 文档
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
ms.openlocfilehash: 1eff579959840f760449422ebbe7af35792e7cc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276533"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a>步骤 3： 为你的组织配置方和业务配置文件
![步骤 3 中 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")  
  
 在此步骤中，你将为组织配置参与方和业务配置文件，以便接收来自贸易合作伙伴的 850 消息，并返回 997 确认消息。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a>为组织配置参与方和业务配置文件  
  
1.  打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，通过单击**启动**，依次指向**所有程序**，依次指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。 右键单击**方**，指向**新建**，然后单击**方**。  
  
3.  在**参与方属性**对话框框中，输入**OrderSystem**中**名称**字段。  
  
4.  选择**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框。 通过选中复选框指定的当事方 (在这种情况下， **OrderSystem**) 也承载 BizTalk Server。  
  
5.  单击 **“确定”**。  
  
6.  右键单击方名称，指向**新建**，然后单击**业务配置文件**。  
  
7.  在**配置文件属性**对话框中，在**常规**页上，输入`OrderSystem_Profile`中**名称**文本框。  
  
    > [!NOTE]
    >  一个配置文件时创建一个参与方，名为*PartyName*_Profile 自动创建。 你可以使用此配置文件，不必创建新的配置文件。 若要重命名配置文件，右键单击配置文件，然后选择**属性**。 在**常规**页上，指定配置文件的名称。  
  
8.  单击 **“确定”**。  
  
## <a name="next-steps"></a>后续步骤  
 为你的合作伙伴组织配置方和业务配置文件 (**Fabrikam**) 中所述，[步骤 4： 为你的贸易合作伙伴配置方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)