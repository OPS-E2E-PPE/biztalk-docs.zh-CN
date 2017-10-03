---
title: "如何为博士 Edwards OneWorld 创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 858425ef-bdb7-4d2d-90ca-b3655e389749
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc77fd72171983ab2fbc7de42ddf36d770d045c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a>如何创建 JD Edwards OneWorld 的发送端口
使用以下过程创建发送端口。  
  
### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后导航到所需的应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
    > [!NOTE]
    >  你还可以使用**静态单向端口**。  
  
3.  在**发送端口属性**对话框中，在**名称**字段中，键入发送端口名称 (例如，键入**SendToJDE**。)  
  
4.  在**类型**下拉列表中，选择**JDEOneWorld**。  
  
5.  在**URI**下拉列表中，选择发送处理程序。  
  
6.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建博士 Edwards OneWorld 发送处理程序](../core/creating-jd-edwards-oneworld-send-handlers.md)