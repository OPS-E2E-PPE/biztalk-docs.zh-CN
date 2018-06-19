---
title: 发布 BizTalk 终结点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e8cc81-c6c7-4269-81e3-8725082a0c98
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e33517f1261324ad01eb0d9cad0f51b74c280828
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294285"
---
# <a name="publishing-biztalk-endpoints"></a>发布 BizTalk 终结点
ESB 管理门户可用于创建和发布到当前配置的通用、 描述、 发现和集成 (UDDI) 服务器的条目。  
  
### <a name="to-publish-a-microsoft-biztalk-server-endpoint-into-the-current-uddi-server"></a>若要将 Microsoft BizTalk Server 终结点发布到当前的 UDDI 服务器  
  
1.  指向**注册表**在门户的主菜单上，选项卡，然后单击**新的注册表条目**以打开[新注册表条目页](../esb-toolkit/new-registry-entry-page.md)。  
  
2.  使用在页面上的下拉列表来筛选终结点类型、 状态和应用程序终结点所在的位置。  
  
3.  单击你想要发布创建 UDDI 注册请求的终结点旁边的箭头图标。  
  
4.  如果管理员启用了自动发布的终结点，门户将自动发布到 UDDI 服务器的新条目。  
  
5.  如果管理员尚未启用自动发布的终结点，请求保留在队列中，直到管理员批准或拒绝请求。