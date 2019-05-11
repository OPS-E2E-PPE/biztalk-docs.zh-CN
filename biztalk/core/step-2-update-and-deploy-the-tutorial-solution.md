---
title: 第 2 步：更新和部署教程解决方案 |Microsoft Docs
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
ms.openlocfilehash: 89dff2034e747374c5fdb08763e5d5fbd9d604a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392699"
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a>第 2 步：更新和部署教程解决方案
![步骤 2 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")  
  
 在此步骤中更新为本教程中，提供的解决方案，然后将生成并部署教程程序集。 出于本教程的目的，必要的架构，自定义发送管道，并已创建映射。 使用映射将 850 EDI 数据转换为订单系统所需的格式。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a>若要启用要在 Visual Studio 中生成的 EDI 入站处理解决方案  
  
1. 启动**Microsoft Visual Studio**以管理员身份。  
  
   > [!CAUTION]
   >  如果你不具有管理员权限启动 Visual Studio，你将部署到解决方案时遇到错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
2. 在 Visual Studio 中，单击**文件**，依次指向**打开**，然后单击**项目/解决方案**。 将移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial，选择**EDI Inbound Processing.sln**，然后单击**打开**。  
  
   > [!NOTE]
   >  本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
3. 右键单击**Inbound_EDI**项目在解决方案资源管理器中，然后选择**属性**。  
  
4. 在控制台树中的**Inbound_EDI 属性页**对话框中，选择**部署**并在**Server**字段确保输入您的计算机名称。  
  
5. 在控制台树中，单击**签名**，然后选择**程序集签名**。 有关**选择一个强密钥名称的文件**，选择\<**新建...** \>并输入**keyfile.snk**作为**密钥文件名称**。 清除**保护密钥文件使用密码**，然后单击**确定**。  
  
6. 关闭**Inbound_EDI 属性页**对话框。  
  
### <a name="to-deploy-the-project"></a>若要将项目部署  
  
1. 在解决方案资源管理器中双击**X12_00401_850.xsd**架构。 确认已打开该映射。  
  
2. 在解决方案资源管理器中双击**Inbound4010850_to_OrderFile.btm**映射。 确认已打开该映射。  
  
   > [!NOTE]
   >  在项目中的 Inbound4010850_to_OrderFile.btm 映射将入站 850 测试消息中的数据映射到传递给 OrderSystem 文件夹 (\toOrderSystem) 的出站 XML 文件。  
  
3. 在解决方案资源管理器中右键单击**Inbound_EDI**项目，然后选择**生成**以生成项目。  
  
4. 在解决方案资源管理器中右键单击**Inbound_EDI**项目，然后选择**部署**来部署项目。  
  
5. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**， \< **所有项目**\> ，然后选择**资源**。 确认**Inbound_EDI**列出的程序集。  
  
## <a name="next-steps"></a>后续步骤  
 为你的组织配置参与方和业务配置文件 (**OrderSystem**)，如中所述[步骤 3:为你的组织配置参与方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
## <a name="see-also"></a>请参阅  
 [步骤 1：EDI 接口开发人员教程的准备工作](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)