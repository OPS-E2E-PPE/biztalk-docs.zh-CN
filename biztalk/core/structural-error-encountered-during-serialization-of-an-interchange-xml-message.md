---
title: 交换 XML 消息序列化期间遇到结构错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97939bfd-d1ee-455a-9952-4f25db020e7c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e5ce0694b60afcb743c138d3059a78f63f6fcb5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994294"
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a>交换 XML 消息序列化期间遇到结构错误
## <a name="details"></a>详细信息  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                                  InvalidXmlNodeFound                                   |
|  消息正文   |    交换 XML 消息序列化期间遇到结构错误     |

## <a name="explanation"></a>解释  
 此错误表明在交换 XML 消息的序列化期间遇到结构错误。 BTS 查找 XML StartElement 或 EndElement，但遇到另一个 XML 节点类型。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保消息结构正确，然后重试：  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后单击**BizTalk 组**。  

3. 在右窗格中，单击**组中心**选项卡。  

4. 单击**挂起的服务实例**。  

5. 双击该消息。  

6. 在中**服务的详细信息**窗口中，单击**消息**选项卡。  

7. 再次双击该消息。  

8. 在左窗格中，单击**消息部件 / 正文**。  

9. 确定消息结构是否正确。
