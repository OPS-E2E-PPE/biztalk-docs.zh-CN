---
title: 步骤 3e:生成和部署 BizTalk Server 解决方案 |Microsoft Docs
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
ms.openlocfilehash: 0ab07af6e0937ff015acc4acdd4e0ad116ea72a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392594"
---
# <a name="step-3e-build-and-deploy-the-biztalk-server-solution"></a>步骤 3e:生成和部署 BizTalk Server 解决方案
在本主题中，我们将部署两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目 (**BtsSalesforceIntegration**并**CustomPipeline**)，我们在前面步骤中创建。  
  
### <a name="to-build-and-deploy-the-biztalk-server-projects"></a>若要生成和部署 BizTalk Server 项目  
  
1. 在解决方案资源管理器，右键单击**BtsSalesforceIntegration** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，然后依次**属性**。  
  
2. 在中**部署**选项卡上，对于**应用程序名称**，输入**SalesforceIntegration**。 单击“保存” 。  
  
3. 同样，用鼠标右键单击**CustomPipeline** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，然后单击**属性**，然后在**部署**选项卡上，为**应用程序名称**属性，输入**SalesforceIntegration**试。 单击“保存” 。 这可确保自定义管道组件部署到同一个应用程序作为**BtsSalesforceIntegration**项目。  
  
4. 右键单击解决方案名称，在解决方案资源管理器，然后单击**属性**。 在解决方案属性页对话框中，单击**配置属性**，并确认**构建**和**部署**选中的复选框均适用**BtsSalesforceIntegration**并**CustomPipeline**项目。  
  
5. 右键单击解决方案资源管理器中的解决方案名称，然后单击**生成解决方案**。 成功生成后，再次右键单击解决方案名称，然后依次**部署解决方案**。 解决方案部署到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="see-also"></a>请参阅  
 [步骤 3：在 Visual Studio 中创建的 BizTalk Server 解决方案](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)