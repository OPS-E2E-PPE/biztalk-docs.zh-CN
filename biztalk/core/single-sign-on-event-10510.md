---
title: 单一登录：Event 10510 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a3ac20c725492ebd6f7867cdf3c11be3ab7fdab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393936"
---
# <a name="single-sign-on-event-10510"></a>单一登录：事件 10510
## <a name="details"></a>详细信息  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  产品名称   |                 企业单一登录                  |
| 产品版本 | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    事件 ID     |                           10510                            |
|  事件源   |                           ENTSSO                           |
|    组件    |                            N\A                             |
|  符号名称  |                  SSO_INFO_DLL_LOAD_FAILED                  |
|  消息正文   |   未能加载 %1。 检查此文件可用。    |

## <a name="explanation"></a>解释  
 此信息事件表明 SSO 服务无法加载 DLL。  

## <a name="user-action"></a>用户操作  
 若要解决此事件，请执行一个或多个以下操作：  

- 验证 DLL 位于 SSO 安装目录，通常 C:\Program Files\Common Files\Enterprise Single Sign-on。 SSO 安装目录中可能会有所不同。  

- 如果单个 DLL 已丢失或损坏，尝试将其替换为，然后重新启动该服务。  

  有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：  

- [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
