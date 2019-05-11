---
title: 单一登录：Event 10520 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91662072-d87c-4290-8afb-2143143ee858
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a711e7ef49d32b85d774438e4e9f42e9805a99a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400233"
---
# <a name="single-sign-on-event-10520"></a>单一登录：事件 10520
## <a name="details"></a>详细信息  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                       企业单一登录                                                        |
| 产品版本 |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    事件 ID     |                                                                 10520                                                                  |
|  事件源   |                                                                 ENTSSO                                                                 |
|    组件    |                                                                  N\A                                                                   |
|  符号名称  |                                                          SSO_WARN_NO_SECRETS                                                           |
|  消息正文   | 主密钥服务器的注册表中未不找到任何密钥。 使用配置工具来生成或还原主密钥。 |

## <a name="explanation"></a>解释  
 此警告事件表明主密钥服务器的注册表中未找到任何密钥。 SSO 主密钥存储在 SSO 主密钥服务器的注册表中加密。 两个密钥通常保存在注册表中： 当前主密钥和之前的主密钥。 使用 GUID (主密钥 id) 标识的机密。 如果请求时在注册表中找不到指定的主密钥，则将返回此错误代码。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行一个或多个以下操作：  

- 检查主密钥服务器名称正确且是否为预期。  

- 如果正确无误，检查是否存在该主密钥服务器的注册表中的主密钥。 主密钥位于 hkey_local_machine\software\microsoft\entsso\ssoss 下 （此密钥是仅在 SSO 主密钥服务器上存在）。  

- 如果缺少该密钥，则主密钥不存在。 应存在名为 Guid 的包含加密的密钥的 SSOSS 下的一个或多个密钥。 如果这些不存在，则主密钥不存在。 为主密钥标识 Guid (主密钥 id) 因此，这些 Guid （如果存在） 应与请求的机密的主密钥 id 匹配。 如果没有名为 Guid 的密钥，但它们与请求的主密钥 id 不匹配，则将混合注册表中的主密钥和用来加密 SSO 数据库 (SSODB) 中的数据的机密。 可能有必要在这种情况下，还原另一个主密钥，或可能已从下层备份还原 SSODB。 如果根本不存在主密钥，然后它可以是从备份还原使用 SSO 配置工具 （命令行或 MMC），也可以生成一个新的机密。 请注意，则通常只需要生成新的主密钥，如果这是新安装并且没有任何现有加密 SSO 数据库中的数据。 通常，第一次在初始配置过程生成主密钥。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [主密钥服务器](../core/master-secret-server.md)  

- [管理主密钥](../core/managing-the-master-secret.md)  

- [配置 SSO](../core/configuring-sso.md)
