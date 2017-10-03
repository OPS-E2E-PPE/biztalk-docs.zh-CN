---
title: "（适用于 Azure) 中的步骤 3： 创建 Service Bus 队列 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55b3222798edb245000cdde8de52565c39758a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a>（适用于 Azure) 中的步骤 3： 创建 Service Bus 队列
在本主题中，你将创建一个 Service Bus 队列，在使用 EDI 协议处理并转换 X12 销售订单后会将其发送至该队列。  
  
### <a name="to-create-a-service-bus-queue"></a>创建 Service Bus 队列的步骤  
  
1.  登录到[Windows Azure CTP 管理门户](http://go.microsoft.com/fwlink/p/?LinkId=202886)使用你的 Microsoft 帐户。  
  
2.  在该页的较低的左侧，单击**AppFabric**。  
  
3.  展开左侧树中的服务，展开你的订阅，然后单击你必定已创建的一个命名空间。 如果你已没有命名空间，请参阅[如何： 创建或修改 Windows Azure CTP 服务 Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx)。  
  
4.  若要创建队列单击**新队列**从**管理实体**从页面顶部的工具栏的类别。  
  
5.  在**新队列**对话框框中，输入队列的名称。 对于本教程中，输入作为名称`queueordersedi`，然后单击**确定**。 在指定此名称为的 EDI 协议的一部分中创建[(为 Azure) 的步骤 2： 创建 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)。  
  
## <a name="see-also"></a>另请参阅  
 [教程 4： 创建使用 BizTalk Server 2013 的混合应用程序](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)