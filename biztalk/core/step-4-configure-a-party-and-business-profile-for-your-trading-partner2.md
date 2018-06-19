---
title: 步骤 4： 为你贸易和 Partner2 配置方和业务配置文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce07a1a6-4d5d-44ea-b1cb-04d7ae85747f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f775a720c6dcc42a3edd22154843a4a9118cc90e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278117"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a>步骤 4： 为贸易合作伙伴配置方和业务配置文件
![步骤 4 11](../core/media/tut-step4-of-11.gif "Tut_Step4_of_11")  
  
 在此步骤中，您将为您的贸易合作伙伴 Fabrikam 配置参与方和业务配置文件，以便向组织发送 864 消息，并接收返回的 997 确认消息和异步 MDN。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a>为你的贸易合作伙伴配置参与方和业务配置文件  
  
1.  打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，通过单击**启动**，依次指向**所有程序**，依次指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**.  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。 右键单击**方**，指向**新建**，然后单击**方**。  
  
3.  在**参与方属性**对话框框中，输入**Fabrikam**中**名称**字段。  
  
4.  清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框。 通过清除复选框指定的当事方 (在这种情况下， **Fabrikam**) 未承载 BizTalk Server。  
  
5.  单击 **“确定”**。  
  
6.  右键单击方名称，指向**新建**，然后单击**业务配置文件**。  
  
7.  在**配置文件属性**对话框中，在**常规**页上，输入`Fabrikam_Profile`中**名称**文本框。  
  
    > [!NOTE]
    >  在创建参与方时，也将创建一个配置文件。 你可以重命名，并使用该配置文件而不是创建一个新。 若要重命名配置文件，右键单击配置文件，然后选择**属性**。 在**常规**页上，指定配置文件的名称。  
  
8.  单击 **“确定”**。  
  
## <a name="next-steps"></a>后续步骤  
 配置 BTS ISAPI 筛选器和 Fabrikam 和 Contoso Web 页[步骤 5： 配置贸易合作伙伴网页](../core/step-5-configure-the-trading-partner-web-pages.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)