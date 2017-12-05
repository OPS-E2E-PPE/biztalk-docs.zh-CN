---
title: "步骤 3： 创建 Contoso LOB 应用程序映射的价格和可用性项目使用 BizTalk 映射程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fef0f6e951798dd2453aa387d8dcde9853968f3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a>步骤 3： 为价格和可用性项目使用 BizTalk 映射程序创建 Contoso LOB 应用程序映射
在此步骤中，将创建两个映射，它们可以用于定义在两个贸易合作伙伴之间成功交换消息所需的转换。 在此方案中，Contoso ERP 系统已对价格与可用性请求的消息格式进行标准化。 这两个映射分别将来自贸易合作伙伴 Fabrikam 的请求和响应消息映射为内部定义的 Contoso 消息，或将内部定义的 Contoso 消息映射为发往贸易合作伙伴 Fabrikam 的请求和响应消息。  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a>为 3A2 PriceAndAvailability 请求架构添加引用  
  
1.  在解决方案资源管理器，右键单击 ContosoPriceAndAvailability 项目，然后单击**添加引用**。  
  
2.  在添加引用对话框中，单击**浏览**。  
  
3.  移动到文件夹*\<驱动器\>*: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin，，然后选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**程序集。  
  
4.  单击**添加**，然后单击**确定**。  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a>创建 3A2 PriceAndAvailability 请求到 Contoso PriceAndAvailability 请求的映射  
  
1.  在解决方案资源管理器，右键单击 ContosoPriceAndAvailability 项目，指向**添加**，然后单击**新项**。  
  
2.  在添加新项-ContosoPriceAndAvailability 对话框中，选择**映射文件**在类别窗格中，然后选择**映射**中**模板**窗格。 在**名称**框中，键入**PIP3A2RequestToContosoPriceRequest**，然后单击**添加**。  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a>为 PIP3A2RequestToContosoPriceRequest 映射关联架构  
  
1.  在 BizTalk 映射程序 （与 PIP3A2RequestToContosoPriceRequest.btm 显示的)，在源架构窗格中，单击**打开源架构**。  
  
2.  在 BizTalk 类型选取器对话框中，展开**ContosoPriceAndAvailability**，展开**引用**，展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，，然后展开**架构。**  
  
3.  选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs。**  
  
     **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**，然后单击**确定**。  
  
4.  在目标架构窗格中，单击**打开目标架构**。  
  
5.  在 BizTalk 类型选取器对话框中，展开**ContosoPriceAndAvailability**，然后展开**架构**。  
  
6.  选择**ContosoPriceAndAvailability.ContosoPriceSchema**架构，，然后单击**确定**。  
  
7.  在目标架构对话框中的根节点中，选择**rootPriceRequest**架构，，然后单击**确定**。  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a>在 PIP3A2RequestToContosoPriceRequest 映射中链接架构字段  
  
1.  在目标架构窗格中，右键单击**\<架构\>**节点，，然后单击**展开树节点**。  
  
2.  在源架构窗格中，右键单击**\<架构\>**节点，，然后单击**展开树节点**。  
  
3.  拖动**GlobalProductIdentifier**字段**ProductID**字段在目标架构窗格中。  
  
    > [!NOTE]
    >  你可以找到**GlobalProductIdentifier**字段中的节点 Pip3A2PriceAndAvailabilityQuery/ProductPriceAndAvailabilityQuery /  
    >   
    >  ProductPriceAndAvailability/ProductLineItem/productUnit/  
    >   
    >  ProductPackageDescription/ProductIdentification 中。  
  
4.  上**文件**菜单上，单击**保存所有**以保存所做的更改。  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置 Contoso 的 BizTalk 端口](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)