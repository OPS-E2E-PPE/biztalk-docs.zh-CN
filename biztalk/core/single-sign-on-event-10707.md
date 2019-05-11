---
title: 单一登录：Event 10707 | Microsoft Docs
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
ms.openlocfilehash: e323f9b712e566278bf43224611b2d39e74dcecb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397275"
---
# <a name="single-sign-on-event-10707"></a>单一登录：事件 10707
## <a name="details"></a>详细信息  

|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                       企业单一登录                                                                        |
| 产品版本 |                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    事件 ID     |                                                                                 10707                                                                                  |
|  事件源   |                                                                                 ENTSSO                                                                                 |
|    组件    |                                                                                  N\A                                                                                   |
|  符号名称  |                                                                        SSO_WARN_PS_NO_APP_SYNC                                                                         |
|  消息正文   | 此适配器的密码同步标志必须允许密码同步，并且必须匹配全局标志。 检查适配器标志和全局 flags.%r<br /><br /> 适配器： %1 |

## <a name="explanation"></a>解释  
 此警告事件表明此适配器的密码同步标志必须允许密码同步，并且必须匹配全局标志。  

 一个由两个标志控制的密码同步适配器的密码同步，允许发送到外部系统 (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) 的密码，另一类允许接收来自外部系统 (SSO_FLAG_PARTIAL_ 密码SYNC_FROM_EXTERNAL_TO_DB)。 这些必须对于成功的密码同步设置这两个"全局标志"，还负责特定适配器标志。 外部密码同步适配器请求密码同步，并且这些标志设置为"全局标志"和适配器标志时，会发出此警告事件。  

## <a name="user-action"></a>用户操作  
 若要解决此警告，请执行以下操作：  

-   使用 SSO Admin MMC 管理单元 (系统&#124;属性&#124;选项) 或命令行工具`ssomanage –enable winsync/extsync`来启用全局标志。  

## <a name="more-info"></a>详细信息

- **企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  

- [如何管理密码同步](../core/how-to-administer-password-synchronization.md)
