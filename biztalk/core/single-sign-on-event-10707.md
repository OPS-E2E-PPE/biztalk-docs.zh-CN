---
title: 单一登录： 事件 10707 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 773ba5034616742f7f63fbc90a848275587b3353
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996726"
---
# <a name="single-sign-on-event-10707"></a>单一登录： 事件 10707
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                       企业单一登录                                                                        |
| 产品版本 |                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    事件 ID     |                                                                                 10707                                                                                  |
|  事件源   |                                                                                 ENTSSO                                                                                 |
|    组件    |                                                                                  N\A                                                                                   |
|  符号名称  |                                                                        SSO_WARN_PS_NO_APP_SYNC                                                                         |
|  消息正文   | 此适配器的密码同步标志必须允许密码同步并且必须匹配全局标志。 请检查适配器标志和全局标志。%r<br /><br /> 适配器： %1 |

## <a name="explanation"></a>解释  
 此警告事件表明此适配器的密码同步标志必须允许密码同步并且必须匹配全局标志。  

 密码同步适配器的密码同步由两个标志控制，一个允许将密码发送到外部系统 (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL)，另一个允许从外部系统接收密码 (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB)。 为成功进行密码同步，这些标志必须都设置为“全局标志”，也可以设置为特定适配器标志。 当外部密码同步适配器请求密码同步，并且这些标志未设置为“全局标志”和适配器标志时，将发出此警告事件。  

## <a name="user-action"></a>用户操作  
 若要解决此警告问题，请执行以下操作：  

-   使用 SSO Admin MMC 管理单元 (系统&#124;属性&#124;选项) 或命令行工具`ssomanage –enable winsync/extsync`来启用全局标志。  

## <a name="more-info"></a>详细信息

- **企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)
