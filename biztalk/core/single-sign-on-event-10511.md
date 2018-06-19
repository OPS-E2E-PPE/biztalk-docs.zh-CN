---
title: 单一登录： 事件 10511 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98371982-0db5-4ae0-9f92-f05a58e23b83
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c080812d70dc78a0fe2a9b217833f961da951401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271509"
---
# <a name="single-sign-on-event-10511"></a>单一登录： 事件 10511
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|企业单一登录|  
|产品版本|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|事件 ID|10511|  
|事件源|ENTSSO|  
|组件|N\A|  
|符号名称|SSO_ERROR_NO_DSN|  
|消息正文|注册表中找不到 SQL Server 和 SSO 数据库的名称。 使用 SSO 管理工具来配置这些值。|  
  
## <a name="explanation"></a>解释  
 此错误事件表明注册表中找不到 SQL Server 和 SSO 数据库的名称。 该 SSO 服务需要使用此信息才能连接到 SSO 数据库。 此信息在配置过程中在注册表中设置。 这可能指示配置未正确完成，或者配置完成后这些注册表项已删除。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  
  
-   如果您担心发生更大范围的配置故障，请对该产品取消配置，然后使用配置程序重新配置。  
  
-   也可以使用 SSO 安装目录（通常为 C:\Program Files\Common Files\Enterprise Single Sign-On）中的 SSO 命令行工具 ssoconfig.exe 来设置这些具体的缺失注册表项。 您的 SSO 安装目录可能有所不同。 使用 **-setDB**选项来设置所需的 SQL Server 和 SSO 数据库名称。  
  
 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  
  
-   [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)