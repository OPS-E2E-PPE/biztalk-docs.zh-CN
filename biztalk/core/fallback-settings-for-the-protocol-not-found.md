---
title: 找不到协议的后备设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d93e5db1-16a3-4796-8fa2-fef934508034
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cbbb9d8d3d2971e202f33784a9b98e3a108f5c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388117"
---
# <a name="fallback-settings-for-the-protocol-not-found"></a>找不到协议的后备设置
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                      AgreementResolutionFallbackSettingsNotFound                       |
|  消息正文   |                   后备设置{0}找不到协议。                    |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 能够解析到某个协议且已重定向到回退设置，但发现特定协议没有回退设置。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请为特定协议配置回退设置。