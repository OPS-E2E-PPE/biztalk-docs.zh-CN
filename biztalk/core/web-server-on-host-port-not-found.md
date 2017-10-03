---
title: "找不到的主机端口上的 web 服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dce09ce00a169ad14bbc8ae2ab28fe70c039c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="web-server-on-host-port-not-found"></a>主机端口上找不到 Web 服务器
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|事件 ID|0|  
|事件源|0|  
|组件|0|  
|符号名称|0|  
|消息正文|Web 服务器上找不到主机"{0}"端口 {1}|  
  
## <a name="explanation"></a>解释  
 此错误表示“万维网 (WWW) 服务”未运行。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程启动“万维网服务”。  
  
#### <a name="to-start-the-world-wide-web-service"></a>启动“万维网服务”的步骤  
  
1.  单击**启动**，单击**控制面板**，双击**管理工具**，双击**服务。**  
  
2.  在名称列中，找到**World Wide Web Publishing**。 确保状态是**已启动**。  
  
3.  返回到**管理工具**窗口。 双击**Internet Information Services**。  
  
4.  展开文件夹区域，然后找到 Web 站点。  
  
5.  确保状态是**已启动**。