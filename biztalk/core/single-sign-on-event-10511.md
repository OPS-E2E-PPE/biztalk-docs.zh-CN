---
title: 单一登录：Event 10511 | Microsoft Docs
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
ms.openlocfilehash: 531e32a2c23c30095dc744c6e73d111ce9cccc13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400244"
---
# <a name="single-sign-on-event-10511"></a>单一登录：事件 10511
## <a name="details"></a>详细信息  

|                 |                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                     企业单一登录                                                     |
| 产品版本 |                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                     |
|    事件 ID     |                                                               10511                                                               |
|  事件源   |                                                              ENTSSO                                                               |
|    组件    |                                                                N\A                                                                |
|  符号名称  |                                                         SSO_ERROR_NO_DSN                                                          |
|  消息正文   | 在注册表中找不到 SQL Server 和 SSO 数据库的名称。 使用 SSO 管理工具来配置这些值。 |

## <a name="explanation"></a>解释  
 此错误事件表示，在注册表中未找到 SQL Server 和 SSO 数据库的名称。 SSO 服务需要使用此信息，以便它可以连接到 SSO 数据库。 在配置期间，如果在注册表中设置此信息。 这可能表示配置未正确完成，或注册表项已被删除后配置已完成。  

## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行下列一项或多项操作:  

- 如果您怀疑更广泛的配置失败，取消对该产品，然后重新配置使用配置程序。  

- 或者可以使用 SSO 命令行工具 ssoconfig.exe SSO 安装目录，通常 C:\Program Files\Common Files\Enterprise Single Sign-on 中设置这些特定的缺失注册表项。 SSO 安装目录中可能会有所不同。 使用 **-setDB**选项设置的所需的 SQL Server 和 SSO 数据库名称。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
