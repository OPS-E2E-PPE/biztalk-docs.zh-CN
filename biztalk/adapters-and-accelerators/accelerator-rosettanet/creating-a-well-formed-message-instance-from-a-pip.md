---
title: "从 PIP 创建格式正确的消息实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040fee5fab56a1e54b777fc7548b8ff28e5b07ec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a>从 PIP 创建格式正确的消息实例
本主题介绍如何生成格式正确的消息实例。 你可以根据合作伙伴接口流程 (PIP) 为消息实例生成模板。 执行此操作后，必须先修改该模板，以确保该模板的格式正确，然后才能添加数据。  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a>根据 PIP 生成消息实例模板  
  
1.  启动**Microsoft Visual Studio 2012**。  
  
2.  上**文件**菜单上，指向**打开**，然后单击**项目**。  
  
3.  找到\<*驱动器*\>files\microsoft BizTalk\<版本\>Accelerator for RosettaNetSDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。  
  
4.  在解决方案资源管理器，展开**RNPIPs**，然后右键单击你想要创建实例 PIP。  
  
5.  单击**生成实例**。  
  
    > [!NOTE]
    >  这将生成一个根据 PIP 命名的文件，该文件名附加“_output”，并具有扩展名 .xml。 “输出”窗格中的语句指明 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 生成的实例的位置。  
  
### <a name="to-modify-the-message-instance-template"></a>修改消息实例模板  
  
1.  在 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 资源管理器中，找到包含该 XML 文件的文件夹，然后双击文件名打开该文件夹。  
  
2.  在所有其他文本前添加指示 XML 版本和编码的 XML 头标记。 例如：  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" ?>  
    ```  
  
3.  在刚添加的行后面，添加指明 DTD 的 DOCTYPE 行。 例如，对于“3A4 采购订单请求”实例，该行如下所示：  
  
    ```  
    <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
    ```  
  
    > [!NOTE]
    >  每个消息实例都必须包括要进行处理的 DOCTYPE 行。  
  
4.  现在可自定义此消息实例以满足你的业务需求。 修改 XML 实例，不在其中使用 XML 命名空间或命名空间前缀。  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)