---
title: 步骤 2： 更新和部署教程解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67fd3d34f25dd409121a3a21c9eb419b4aadce6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973411"
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a>步骤 2： 更新和部署教程解决方案
![步骤 2 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 在此步骤中，你将更新为本教程提供的解决方案，然后生成并部署教程程序集。 为了实现本教程的目标，已创建必要的架构、自定义发送管道和映射。 映射用于将 850 EDI 数据转换为订单系统所需的格式。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a>允许在 Visual Studio 中生成 EDI 入站处理解决方案  
  
1.  启动**Microsoft Visual Studio**以管理员身份。  
  
    > [!CAUTION]
    >  如果你不以管理员权限启动 Visual Studio，则向 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署解决方案时，可能会收到错误。  
  
2.  在 Visual Studio 中，单击**文件**，指向**打开**，然后单击**项目/解决方案**。 将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员教程中，选择**EDI 入站 Processing.sln**，然后单击**打开**。  
  
    > [!NOTE]
    >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
3.  右键单击**Inbound_EDI**项目在解决方案资源管理器，，然后选择**属性**。  
  
4.  在控制台树中的**Inbound_EDI 属性页**对话框中，选择**部署**并在**服务器**字段确保输入你的计算机名。  
  
5.  在控制台树中，单击**签名**，然后选择**对程序集签名**。 有关**选择强密钥名称文件**，选择\<**新建...** \>并输入**keyfile.snk**作为**密钥文件名称**。 清除**保护我使用密码的密钥文件**，然后单击**确定**。  
  
6.  关闭**Inbound_EDI 属性页**对话框。  
  
### <a name="to-deploy-the-project"></a>若要将项目部署  
  
1.  在解决方案资源管理器中，双击**X12_00401_850.xsd**架构。 确认已打开该映射。  
  
2.  在解决方案资源管理器中，双击**Inbound4010850_to_OrderFile.btm**映射。 确认已打开该映射。  
  
    > [!NOTE]
    >  项目中的 Inbound4010850_to_OrderFile.btm 映射将入站 850 测试消息中的数据映射到传送给 OrderSystem 文件夹 (\toOrderSystem) 的出站 XML 文件。  
  
3.  在解决方案资源管理器，右键单击**Inbound_EDI**项目，然后选择**生成**以生成项目。  
  
4.  在解决方案资源管理器，右键单击**Inbound_EDI**项目，然后选择**部署**部署项目。  
  
5.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**， \< **所有项目**\> ，然后选择**资源**。 验证**Inbound_EDI**列出的程序集。  
  
## <a name="next-steps"></a>后续步骤  
 为你的组织配置方和业务配置文件 (**OrderSystem**) 中所述，[步骤 3： 为你的组织配置方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
## <a name="see-also"></a>另请参阅  
 [步骤 1：EDI 接口开发人员教程的准备工作](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)