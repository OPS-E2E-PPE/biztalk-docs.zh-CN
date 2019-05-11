---
title: 根据 PIP 创建格式正确的消息实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc0dc9610b171ffa2049c5a4951d3846451aa2db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284685"
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a>根据 PIP 创建格式正确的消息实例
本主题介绍如何生成格式正确的消息实例。 从合作伙伴接口流程 (PIP) 都可以生成消息实例模板。 完成后，必须修改该模板，以便它的格式正确，然后再添加你的数据。  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a>若要从 PIP 生成消息实例模板  
  
1. 启动**Microsoft Visual Studio 2012**。  
  
2. 上**文件**菜单，依次指向**打开**，然后单击**项目**。  
  
3. 找到\<*驱动器*\>\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNetSDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。  
  
4. 在解决方案资源管理器，展开**Rnpip**，然后右键单击您要为其创建实例的 PIP。  
  
5. 单击**生成实例**。  
  
   > [!NOTE]
   >  这将生成名为 pip"_output"追加到的文件名和扩展名为.xml 文件。 输出窗格中的语句指示的位置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]生成的实例。  
  
### <a name="to-modify-the-message-instance-template"></a>若要修改消息实例模板  
  
1. 在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，找到包含 XML 文件的文件夹并双击要打开的文件夹的文件名称。  
  
2. 添加之前，该值指示的 XML 并将编码版本的所有其他文本的 XML 头标记。 例如：  
  
   ```  
   <?xml version="1.0" encoding="UTF-8" ?>  
   ```  
  
3. 刚添加的行之后, 添加指明 DTD 的 DOCTYPE 行。 例如，对于 3A4 采购订单请求实例，行是按如下所示：  
  
   ```  
   <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
   ```  
  
   > [!NOTE]
   >  每个消息实例必须包含要处理的 DOCTYPE 行。  
  
4. 现在，您可以自定义此消息实例以满足你的业务需求。 修改 XML 实例，使它不使用 XML 命名空间或命名空间前缀。  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)