---
title: 步骤 3：创建 Contoso LOB 应用程序的价格与可用性项目使用 BizTalk 映射器将映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d7a1289bc11517e97bac706803ad0c78dbc2d5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281150"
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a>步骤 3：为价格与可用性项目使用 BizTalk 映射器中创建的 Contoso LOB 应用程序映射
在此步骤中，将创建两个定义两个贸易合作伙伴之间成功交换消息所需的转换的映射。 对于此方案，Contoso ERP 系统已进行了标准化的价格与可用性请求的消息格式。 两个映射将来自贸易合作伙伴 （Fabrikam) 的请求和响应消息与这些内部定义的 Contoso 消息，分别映射。  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a>若要添加为 3A2 PriceAndAvailability 请求架构的引用  
  
1.  在解决方案资源管理器，右键单击 ContosoPriceAndAvailability 项目中，然后依次**添加引用**。  
  
2.  在添加引用对话框中，单击**浏览**。  
  
3.  转到的文件夹*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin，然后选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**程序集。  
  
4.  单击**外**，然后单击**确定**。  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a>若要创建 3A2 PriceAndAvailability 请求到 Contoso PriceAndAvailability 请求的映射  
  
1.  在解决方案资源管理器中右键单击 ContosoPriceAndAvailability 项目，指向**外**，然后单击**新项**。  
  
2.  在添加新项-ContosoPriceAndAvailability 对话框中，选择**地图文件**在类别窗格中，然后选择**地图**中**模板**窗格。 在中**名称**框中，键入**PIP3A2RequestToContosoPriceRequest**，然后单击**添加**。  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a>要关联为 PIP3A2RequestToContosoPriceRequest 映射架构  
  
1.  在 BizTalk 映射器 (显示 pip3a2requesttocontosopricerequest.btm)，在源架构窗格中，单击**打开源架构**。  
  
2.  在 BizTalk 类型选取器对话框中，展开**ContosoPriceAndAvailability**，展开**引用**，展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，，然后展开**架构。**  
  
3.  选择**Microsoft.Solutions.BTARN.Schemas.RNPIPs。**  
  
     **_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**，然后单击**确定**。  
  
4.  在目标架构窗格中，单击**打开目标架构**。  
  
5.  在 BizTalk 类型选取器对话框中，展开**ContosoPriceAndAvailability**，然后展开**架构**。  
  
6.  选择**ContosoPriceAndAvailability.ContosoPriceSchema**架构中，并单击**确定**。  
  
7.  在目标架构对话框的根节点中，选择**rootPriceRequest**架构中，并单击**确定**。  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a>若要 PIP3A2RequestToContosoPriceRequest 映射中链接架构字段  
  
1.  在目标架构窗格中，右键单击**\<架构\>** 节点，，然后单击**展开树节点**。  
  
2.  在源架构窗格中，右键单击**\<架构\>** 节点，，然后单击**展开树节点**。  
  
3.  拖动**GlobalProductIdentifier**字段**ProductID**字段在目标架构窗格中。  
  
    > [!NOTE]
    >  您可以找到**GlobalProductIdentifier**字段中的节点 Pip3A2PriceAndAvailabilityQuery 它 /  
    >   
    >  ProductPriceAndAvailability/ProductLineItem/productUnit/  
    >   
    >  ProductPackageDescription/ProductIdentification.  
  
4.  上**文件**菜单上，单击**全部保存**以保存所做的更改。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置 Contoso 的 BizTalk 端口](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)