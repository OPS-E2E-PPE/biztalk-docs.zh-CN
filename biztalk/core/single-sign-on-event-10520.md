---
title: 单一登录： 事件 10520 |Microsoft Docs
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
ms.openlocfilehash: 0721ae4d89ee05792f2189a0d6a6b2c5e4efdddb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011382"
---
# <a name="single-sign-on-event-10520"></a>单一登录： 事件 10520
## <a name="details"></a>详细信息  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                       企业单一登录                                                        |
| 产品版本 |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    事件 ID     |                                                                 10520                                                                  |
|  事件源   |                                                                 ENTSSO                                                                 |
|    组件    |                                                                  N\A                                                                   |
|  符号名称  |                                                          SSO_WARN_NO_SECRETS                                                           |
|  消息正文   | 未在主密钥服务器的注册表中找到任何密钥。 请使用配置工具来生成或还原主密钥。 |

## <a name="explanation"></a>解释  
 此警告事件表明，未在主密钥服务器的注册表中找到任何密钥。 SSO 主密钥以加密形式存储在 SSO 主密钥服务器的注册表中。 两个密钥通常保存在注册表中： 当前主密钥和之前的主密钥。 密钥使用 GUID（主密钥 ID）标识。 如果请求指定的主密钥时无法在注册表中找到该主密钥，则将返回此错误代码。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行下列一项或多项操作：  

- 检查主密钥服务器名称是否正确，且是否为预期的名称。  

- 如果正确，则检查该主密钥服务器的注册表中是否存在该主密钥。 该主密钥位于 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS 下（此密钥仅存在于 SSO 主密钥服务器上）。  

- 如果该密钥缺失，则主密钥不存在。 SSOSS 下应存在一个或多个包含加密密钥的名为 GUID 的密钥。 如果这些密钥不存在，则主密钥不存在。 主密钥以 GUID（主密钥 ID）标识，因此，这些 GUID（如果存在）应与所请求的密钥的主密钥 ID 匹配。 如果存在名为 GUID 的密钥，但它们与所请求的主密钥 ID 不匹配，则将混合注册表中的主密钥与用于对 SSO 数据库 (SSODB) 中的数据进行加密的密钥。 在这种情况下，可能必须还原另一个主密钥，或者 SSODB 已从下层备份还原。 如果根本不存在主密钥，则可以使用 SSO 配置工具（命令行或 MMC）从备份还原该主密钥，或者生成一个新密钥。 请注意，如果这是新安装，且 SSO 数据库中不存在任何现有的已加密数据，则通常只需要生成一个新主密钥。 主密钥通常是在初始配置过程中首次生成的。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [主密钥服务器](../core/master-secret-server.md)  

- [管理主密钥](../core/managing-the-master-secret.md)  

- [配置 SSO](../core/configuring-sso.md)
