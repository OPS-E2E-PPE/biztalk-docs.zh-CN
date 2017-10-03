---
title: "步骤 1： 将现有 BizTalk 项目添加到现有的 Contoso 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, adding to solutions
- private process tutorial, adding projects to solutions
ms.assetid: 9e84d282-01aa-4611-8462-c1acef234042
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c6a6bd5807702cb01c4c7cbc13780b95cc3da2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-adding-an-existing-biztalk-project-to-the-existing-contoso-solution"></a>步骤 1： 将现有 BizTalk 项目添加到现有的 Contoso 解决方案
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 包含专用业务流程，在自定义你自己的专用流程时它是一个很好的起点。 在此步骤中，将该业务流程添加到解决方案，然后更改程序集的名称，以避免此名称与 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装过程中安装的 PrivateResponder 业务流程相冲突。 在开始之前，打开你在中创建 Contoso 解决方案[步骤 1： 为 Contoso 价格和可用性请求创建一个新的 BizTalk 解决方案](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)。  
  
### <a name="to-add-the-privateresponder-project-to-the-contoso-solution"></a>向 Contoso 解决方案添加 PrivateResponder 项目  
  
1.  将 PrivateResponder SDK 示例复制到 Contoso 解决方案文件夹中。  
  
    > [!NOTE]
    >  默认情况下，PrivateResponder SDK 示例位于 C:\Program Files\Microsoft BizTalk\<版本 > Accelerator for RosettaNet\SDK\PrivateResponder 文件夹。  
  
2.  在 Visual Studio 中，单击**文件**，指向**添加**，然后单击**现有项目**。  
  
3.  在添加现有项目对话框中，找到你的解决方案中，选择的文件夹**PrivateResponder.btproj**项目文件，，然后单击**打开**。  
  
### <a name="to-change-the-privateresponder-assembly-name-and-default-namespace"></a>更改 PrivateResponder 程序集名称和默认命名空间  
  
1.  在解决方案资源管理器，右键单击**PrivateResponder**项目，，然后单击**属性**。  
  
2.  在控制台树中，PrivateResponder 属性页对话框中单击**常规**。 在详细信息窗格中，在**程序集名称**框中，键入**ContosoPriceAndAvailability.PrivateResponder**。  
  
3.  在**默认 Namespace**框中，键入**ContosoPriceAndAvailability**。  
  
4.  单击**确定**以关闭 PrivateResponder 属性页对话框。  
  
5.  在解决方案资源管理器中，双击**PrivateResponder.odx**。  
  
6.  在**业务流程视图**窗口中，确保**业务流程属性**(下**PrivateResponderProcess**) 选择。  
  
7.  在**属性**窗口，请在**Namespace**字段中，键入**ContosoPriceAndAvailability**，然后按**Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 定义和 contoso 发布词汇](../../adapters-and-accelerators/accelerator-rosettanet/step-2-defining-and-publishing-the-vocabulary-for-contoso.md)