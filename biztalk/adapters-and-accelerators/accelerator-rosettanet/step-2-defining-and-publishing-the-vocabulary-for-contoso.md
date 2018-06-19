---
title: 步骤 2： 定义和 contoso 发布词汇 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, creating
- vocabularies, publishing
- private process tutorial, creating vocabularies
ms.assetid: e23880c0-772c-48c6-a6b5-32eb951527c8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15937a1235cc1776be38fe2b0e5529c19d3f6fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211085"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a>步骤 2： 定义和 contoso 发布词汇
在此方案中，Contoso 将实现一个业务策略，该策略确保在出现紧急情况时始终有可用库存。 您将使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 中的业务规则编辑器来创建业务策略。 在此步骤中，您将创建定义业务策略时所使用的词汇。  
  
### <a name="to-add-a-new-vocabulary"></a>添加新词汇  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。  
  
2.  在打开规则存储对话框中，单击**确定**。  
  
3.  在事实数据资源管理器窗格中，在**词汇**选项卡上，右键单击**词汇**，然后单击**添加新词汇**。  
  
4.  命名词汇**3A2PriceAvailabilityVocabulary**，然后按**Enter**。  
  
### <a name="to-define-a-constant-vocabulary-value"></a>定义词汇常数值  
  
1.  在业务规则编辑器，单击**3A2PriceAvailabilityVocabulary**，右键单击 **（不保存） 1.0 版**，然后单击**添加新定义**。  
  
2.  上**词汇定义向导**页上，选择**常量值、 值的范围或设置的值**，然后单击**下一步**。  
  
3.  上**常量值、 值的范围或设置的值**页上，在**定义名称**框中，键入**紧急数量需要**，然后单击**下一步**.  
  
4.  上**定义的常量值**页上，在**值**框中，键入**800**，然后单击**完成**。  
  
### <a name="to-define-an-xml-document-get-element"></a>定义 XML 文档的“Get”元素  
  
1.  在业务规则编辑器，在事实数据资源管理器窗格中，右键单击 **（不保存） 1.0 版**下**3A2PriceAvailabilityVocabulary**，然后单击**添加新定义**.  
  
2.  上**VocabularyDefinition 向导**页上，选择**XML 文档元素或属性**，然后单击**下一步**。  
  
3.  上**XML 文档元素或属性**页上，在**定义名称**框中，键入**数量可用**。  
  
4.  单击**浏览**(旁边**架构**字段)，将移到**ContosoPriceAndAvailability**解决方案文件夹，选择中的项目**ContosoPriceAndAvailability.xsd**架构，，然后单击**打开**。  
  
5.  在选择绑定对话框中，展开**rootPriceResponse**，展开**产品**，选择**NumberAvailable**元素，，然后单击**确定**.  
  
6.  上**XML 文档元素或属性**页上，在**文档类型**框中，确保值**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  在**选择操作**部分中，选择**执行"Get"操作**，然后单击**完成**。  
  
### <a name="to-define-an-xml-document-set-element"></a>定义 XML 文档的“Set”元素  
  
1.  在业务规则编辑器，在事实数据资源管理器窗格中，右键单击 **（不保存） 1.0 版**下**3A2PriceAvailabilityVocabulary**，然后单击**添加新定义**.  
  
2.  上**VocabularyDefinition 向导**页上，选择**XML 文档元素或属性**，然后单击**下一步**。  
  
3.  上**XML 文档元素或属性**页上，在**定义名称**框中，键入**最终数量可用**。  
  
4.  单击**浏览**(旁边**架构**字段)，将移到**ContosoPriceAndAvailability**解决方案文件夹，选择中的项目**ContosoPriceAndAvailability.xsd**架构，，然后单击**打开**。  
  
5.  在**选择绑定**对话框框中，展开**rootPriceResponse**，展开**产品**，然后选择**NumberAvailable**元素。 单击 **“确定”**。  
  
6.  上**XML 文档元素或属性**页上，在**文档类型**框中，确保值**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.  
  
7.  在**选择操作**部分中，选择**执行"设置"操作**，然后单击**下一步**。  
  
8.  在**指定的显示名称**页上，单击**完成**。  
  
### <a name="to-save-and-publish-the-vocabulary"></a>保存和发布词汇  
  
1.  在业务规则编辑器，在事实数据资源管理器窗格中，右键单击 **（不保存） 1.0 版**下**3A2PriceAvailabilityVocabulary**，然后单击**保存**。  
  
2.  右键单击该相同**版本 1.0**节点，然后单击**发布**。  
  
    > [!NOTE]
    >  保持业务规则编辑器为打开状态，以执行教程中的下一个步骤。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 定义、 发布和部署为 Contoso 的业务策略](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)