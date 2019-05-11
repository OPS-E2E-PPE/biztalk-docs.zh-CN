---
title: 如何创建适配器处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, handlers [adapters]
- handlers [adapters], creating
- adapters, handlers
ms.assetid: 09569417-dce6-473d-891f-6fd12347bcf0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1e8a8d40beebd93865d657d2a09fc08dc11579a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385533"
---
# <a name="how-to-create-an-adapter-handler"></a>如何创建适配器处理程序
您可以创建一个发送或接收适配器处理程序使用 BizTalk Server 管理控制台。  
  
> [!NOTE]
>  必须是要创建适配器处理程序的单一登录管理员组的成员。  
  
### <a name="to-create-an-adapter-handler"></a>若要创建适配器处理程序  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，右键单击为其想要添加一个发送或接收处理程序，指向的适配器**新建**，然后单击**发送处理程序**来创建发送处理程序，或单击**接收处理程序**创建接收处理程序。  
  
3.  在中**\<主机名\>属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择与主机适配器将处理程序关联。  
  
4.  如果要创建的适配器发送处理程序，选择选项**将此项的默认处理程序**你是否希望此属性为此适配器的默认发送处理程序。  
  
5.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [创建和删除适配器处理程序](../core/creating-and-deleting-adapter-handlers.md)