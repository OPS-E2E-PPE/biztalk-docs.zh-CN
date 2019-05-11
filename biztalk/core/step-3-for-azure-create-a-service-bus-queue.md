---
title: 步骤 3 （适用于 Azure):创建服务总线队列 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fe6744ab7f12b539efb9a91627abe9111373e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392615"
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a>步骤 3 （适用于 Azure):创建服务总线队列
在本主题中，你创建服务总线队列到 X12 销售订单发送后它处理并转换使用 EDI 协议。  
  
### <a name="to-create-a-service-bus-queue"></a>若要创建服务总线队列  
  
1.  登录到[Windows Azure CTP 管理门户](http://go.microsoft.com/fwlink/p/?LinkId=202886)使用你的 Microsoft 帐户。  
  
2.  在较低的页的左侧，单击**AppFabric**。  
  
3.  在左侧树中展开服务，展开你的订阅，然后单击你必须已创建的命名空间。 如果你尚未拥有一个命名空间，请参阅[如何：创建或修改 Windows Azure CTP 服务 Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx)。  
  
4.  若要创建一个队列依次单击**新队列**从**管理实体**在页面顶部工具栏中的类别。  
  
5.  在中**新队列**对话框框中，输入队列的名称。 对于本教程中，输入作为名称`queueordersedi`，然后单击**确定**。 此名称指定为一部分的 EDI 协议中创建[步骤 2 (用于 Azure):创建 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)。  
  
## <a name="see-also"></a>请参阅  
 [教程 4：创建混合应用程序使用 BizTalk Server 2013](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)