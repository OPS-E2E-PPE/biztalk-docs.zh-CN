---
title: "如何创建一个适配器处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, handlers [adapters]
- handlers [adapters], creating
- adapters, handlers
ms.assetid: 09569417-dce6-473d-891f-6fd12347bcf0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dbd0658b43d9e042718153654a4c2666a01feb5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-adapter-handler"></a>如何创建一个适配器处理程序
可以使用 BizTalk Server 管理控制台来创建发送或接收适配器处理程序。  
  
> [!NOTE]
>  您必须是 Single Sign-On Administrators 组的成员，才能创建适配器处理程序。  
  
### <a name="to-create-an-adapter-handler"></a>创建适配器处理程序  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。  
  
2.  在展开的适配器列表中，右键单击的适配器，你想要添加发送或接收处理程序，请指向**新建**，然后单击**发送处理程序**创建发送处理程序，或单击**接收处理者**创建接收处理程序。  
  
3.  在**\<主机名 > 属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择将与之适配器处理程序主机关联。  
  
4.  如果要创建适配器发送处理程序，选择该选项以**将此项的默认处理**你是否希望此项为此适配器的默认发送处理程序。  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和删除适配器处理程序](../core/creating-and-deleting-adapter-handlers.md)