---
title: 步骤 3：定义、 发布和部署 Contoso 业务策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deploying
- policies, publishing
- private process tutorial, creating policies
- policies, creating
ms.assetid: 529b16d8-226b-4046-a95d-64162ebd59a3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0b94deb38356325c81dd1b5192c726e75a43ff0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281105"
---
# <a name="step-3-defining-publishing-and-deploying-the-business-policy-for-contoso"></a>步骤 3：定义、 发布和部署 Contoso 业务策略
在此步骤中，创建一个业务策略，保留一定的 Contoso 所制造用于在紧急情况下每个产品的数量。  
  
### <a name="to-add-a-new-policy"></a>若要添加新的策略  
  
1.  在策略浏览器窗格中的业务规则编辑器中右键单击**策略**，然后单击**添加新策略**。  
  
2.  新策略命名**3A2PriceAvailabilityPolicy**，然后按**Enter**。  
  
### <a name="to-add-a-policy-rule-to-enforce-the-emergency-quantity-needs"></a>若要添加策略规则，以实施应急数量需求  
  
1.  右键单击**版本 1.0 （未保存）** 下**3A2PriceAvailabilityPolicy**，然后单击**添加新规则**。  
  
2.  命名规则**应急供应规则-数量已尽**，然后按**Enter**。  
  
3.  在业务规则编辑器中，在右窗格中，右键单击**条件**在如果窗格中，依次指向**谓词**，然后单击**小于等于**谓词。  
  
4.  在事实浏览器窗格中，展开**词汇**，展开**3A2PriceAvailabilityVocabulary**，展开**版本 1.0-已发布**，选择**数量可用**，并将其拖动到`argument1`占位符上编辑器图面。  
  
5.  重复步骤 4 通过拖动**紧急情况下所需的数量**拖动到`argument2`占位符。  
  
6.  选择**最终可用数量**，然后将其拖到拖**操作**那么窗格中。  
  
### <a name="to-add-a-policy-to-revise-the-number-available-field-in-the-response"></a>若要添加用于修改响应中的可用数量字段的策略  
  
1.  右键单击**版本 1.0 （未保存）** 下**3A2PriceAvailabilityPolicy**，然后单击**添加新规则**。  
  
2.  新规则命名**应急供应规则-可用数量**，然后按**Enter**。  
  
3.  在业务规则编辑器中，在右窗格中，右键单击**条件**在如果窗格中，依次指向**谓词**，然后单击**大于**谓词。  
  
4.  在事实浏览器窗格中，展开**词汇**，展开**3A2PriceAvailabilityVocabulary**，展开**版本 1.0-已发布**，选择**数量可用**，然后将其拖到拖`argument1`占位符上编辑器图面。  
  
5.  重复该步骤所需拖**紧急情况下所需的数量**拖动到`argument2`占位符。  
  
6.  选择**最终可用数量**，然后将其拖到拖**操作**那么窗格中。  
  
7.  在事实浏览器窗格中，展开**版本 1.0-已发布**下**函数**，并将其拖`Subtract`函数拖到**0**下一步参数**最终可用数量**那么窗格中。  
  
8.  拖动**Quantity Available** (下**3A2PriceAvailabilityVocabulary**) 并将其放置在`value1`那么窗格中的占位符。  
  
9. 拖动**紧急情况下所需的数量**，并将其放置在`value2`那么窗格中的占位符。  
  
### <a name="to-save-publish-and-deploy-the-business-policy"></a>若要保存、 发布和部署业务策略  
  
1.  在策略浏览器窗格中，右键单击**版本 1.0 （未保存）** 下**3A2PriceAvailabilityPolicy**，然后单击**保存**。  
  
2.  右键单击该同一个节点，然后依次**发布**。  
  
3.  右键单击该同一个节点，然后依次**部署**。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：创建 HeaderHelper 项目](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)