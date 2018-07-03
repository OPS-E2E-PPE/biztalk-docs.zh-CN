---
title: 找不到主机端口上的 web 服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c253fd5e-b815-4697-a06d-67af65a35589
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62f9260f477669debf709ba592568a15fbaf7194
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987142"
---
# <a name="web-server-on-host-port-not-found"></a>主机端口上找不到 Web 服务器
## <a name="details"></a>详细信息  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |                    主机上的 web 服务器"{0}"端口{1}找不到                     |
  
## <a name="explanation"></a>解释  
 此错误表示“万维网 (WWW) 服务”未运行。  
  
## <a name="user-action"></a>用户操作  
 使用以下过程启动“万维网服务”。  
  
#### <a name="to-start-the-world-wide-web-service"></a>启动“万维网服务”的步骤  
  
1.  单击**启动**，单击**控制面板**，双击**管理工具**，然后双击**服务。**  
  
2.  在名称列中找到**World Wide Web Publishing**。 确保状态为**已启动**。  
  
3.  返回到**管理工具**窗口。 双击**Internet 信息服务**。  
  
4.  展开文件夹区域，然后找到 Web 站点。  
  
5.  确保状态为**已启动**。