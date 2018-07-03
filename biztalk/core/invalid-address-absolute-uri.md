---
title: 地址无效 (绝对 uri) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5db292ad-9105-492d-a6c5-a7108159901a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 933897545d47e2a68c1911474a3549931edd4512
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001246"
---
# <a name="invalid-address-absolute-uri"></a>地址无效（绝对 URI）
## <a name="details"></a>详细信息  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  产品名称   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 产品版本 |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    事件 ID     |                                         0                                          |
|  事件源   |                                         0                                          |
|    组件    |                                         0                                          |
|  符号名称  |                                         0                                          |
|  消息正文   |              无效的地址;"{0}"不是格式正确的绝对 uri              |

## <a name="explanation"></a>解释  
 此错误事件表明您未提供具有正确格式的绝对地址的进程内 WCF 传输。 例如，您无法将进程内 WCF 传输的“地址”属性设置为相对地址（例如 /path/service.svc）。  

## <a name="user-action"></a>用户操作  
 将进程内 WCF 传输的地址更改为格式正确的绝对地址。  

1. 单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。  

2. 在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。  

3. 找到你的应用程序，然后找到您的传输。  

4. 右键单击传输名称。  

5. 单击 **“属性”**。  

6. 在端口**类型**列表中，选择正确的端口。  

7. 单击**配置**。  

8. 在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。  

9. 在中**地址 (URI)** 文本框。 更改的地址。 格式正确的绝对地址的一个示例是 http://localhost/path/service.svc
