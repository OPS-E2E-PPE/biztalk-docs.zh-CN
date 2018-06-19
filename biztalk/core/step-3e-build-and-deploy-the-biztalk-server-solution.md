---
title: 步骤 3e： 生成并部署 BizTalk Server 解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfc382b-ed4a-4401-9343-be1bffd747c9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a970a8f7adb450156b89849eb986c84fd05ab55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276621"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a>步骤 3e： 生成并部署 BizTalk 服务器解决方案
在本主题中，我们会将两个部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目 (**BtsSalesforceIntegration**和**CustomPipeline**)，我们在之前的步骤中创建。  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a>生成和部署 BizTalk Server 项目  
  
1.  在解决方案资源管理器，右键单击**BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，，然后单击**属性**。  
  
2.  在**部署**选项卡上，为**应用程序名称**，输入**SalesforceIntegration**。 单击 **“保存”**。  
  
3.  同样，右键单击**CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目中，单击**属性**，然后在**部署**选项卡上，为**应用程序名称**属性，输入**SalesforceIntegration**试。 单击 **“保存”**。 这将确保自定义管道组件部署到相同的应用程序作为**BtsSalesforceIntegration**项目。  
  
4.  右键单击解决方案名称在解决方案资源管理器，然后单击**属性**。 在解决方案属性页对话框中，单击**配置属性**，并确认**生成**和**部署**选中的复选框均适用**BtsSalesforceIntegration**和**CustomPipeline**项目。  
  
5.  右键单击解决方案资源管理器中的解决方案名称，然后单击**生成解决方案**。 成功生成解决方案后，再次右键单击解决方案名称，并依次**部署解决方案**。 此时，该解决方案将部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 在 Visual Studio 中创建 BizTalk 服务器解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)