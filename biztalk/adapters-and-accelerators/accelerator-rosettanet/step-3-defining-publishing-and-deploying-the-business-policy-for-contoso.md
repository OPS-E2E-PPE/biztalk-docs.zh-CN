---
title: "步骤 3： 定义、 发布和部署为 Contoso 的业务策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, deploying
- policies, publishing
- private process tutorial, creating policies
- policies, creating
ms.assetid: 529b16d8-226b-4046-a95d-64162ebd59a3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbdd1133145aada8b1a1abf0ccdde25547b7fed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-defining-publishing-and-deploying-the-business-policy-for-contoso"></a>步骤 3： 定义、 发布和部署为 Contoso 的业务策略
在此步骤中，您将创建一个业务策略，该策略对于 Contoso 所制造的每种产品都保留一定的数量，以应付紧急情况。  
  
### <a name="to-add-a-new-policy"></a>添加新策略  
  
1.  在业务规则编辑器，在策略资源管理器窗格中，右键单击**策略**，然后单击**添加新策略**。  
  
2.  命名新策略**3A2PriceAvailabilityPolicy**，然后按**Enter**。  
  
### <a name="to-add-a-policy-rule-to-enforce-the-emergency-quantity-needs"></a>添加用于实施应急数量需求的策略规则  
  
1.  右键单击**（不保存） 1.0 版**下**3A2PriceAvailabilityPolicy**，然后单击**添加新规则**。  
  
2.  命名规则**紧急情况下提供规则-数量用完**，然后按**Enter**。  
  
3.  在业务规则编辑器，在右窗格中，右键单击**条件**下的 IF 窗格中，依次指向**谓词**，然后单击**小于等于**谓词。  
  
4.  在事实数据资源管理器窗格中，展开**词汇**，展开**3A2PriceAvailabilityVocabulary**，展开**版本 1.0-发布**，选择**数量可用**，并将其拖动到`argument1`编辑器图面上的占位符。  
  
5.  重复步骤 4 通过拖动**紧急数量需要**到`argument2`占位符。  
  
6.  选择**最终数量可用**，然后将其拖到和**操作**然后窗格中。  
  
### <a name="to-add-a-policy-to-revise-the-number-available-field-in-the-response"></a>添加用于修改响应中的“可用数量”字段的策略  
  
1.  右键单击**（不保存） 1.0 版**下**3A2PriceAvailabilityPolicy**，然后单击**添加新规则**。  
  
2.  将新规则命名为**紧急情况下提供规则-数量可用**，然后按**Enter**。  
  
3.  在业务规则编辑器，在右窗格中，右键单击**条件**下的 IF 窗格中，依次指向**谓词**，然后单击**大于**谓词。  
  
4.  在事实数据资源管理器窗格中，展开**词汇**，展开**3A2PriceAvailabilityVocabulary**，展开**版本 1.0-发布**，选择**数量可用**，然后将其拖到和`argument1`编辑器图面上的占位符。  
  
5.  重复该相同的步骤，通过拖动**紧急数量需要**到`argument2`占位符。  
  
6.  选择**最终数量可用**，然后将其拖到和**操作**然后窗格中。  
  
7.  在事实数据资源管理器窗格中，展开**版本 1.0-发布**下**函数**，并将其拖`Subtract`函数拖到**0**参数旁边**最终数量可用**然后窗格中。  
  
8.  拖动**数量可用**(下**3A2PriceAvailabilityVocabulary**) 并将其放在`value1`然后窗格中的占位符。  
  
9. 拖动**紧急数量需要**，并将其放在`value2`然后窗格中的占位符。  
  
### <a name="to-save-publish-and-deploy-the-business-policy"></a>保存、发布和部署业务策略  
  
1.  在策略资源管理器窗格中，右键单击**（不保存） 1.0 版**下**3A2PriceAvailabilityPolicy**，然后单击**保存**。  
  
2.  右键单击该相同的节点，并依次**发布**。  
  
3.  右键单击该相同的节点，并依次**部署**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 创建 HeaderHelper 项目](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)