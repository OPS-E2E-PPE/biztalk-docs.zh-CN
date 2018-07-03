---
title: 单一登录： 事件 10510 |Microsoft Docs
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
ms.openlocfilehash: 6043dabf397bb987b58707885cbf91d36de50eab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011342"
---
# <a name="single-sign-on-event-10510"></a>单一登录： 事件 10510
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
 此信息事件表示 SSO 服务加载 DLL 失败。  

## <a name="user-action"></a>用户操作  
 若要解决此事件，请执行下列一项或多项操作：  

- 验证该 DLL 是否位于 SSO 安装目录中，通常为 C:\Program Files\Common Files\Enterprise Single Sign-On。 您的 SSO 安装目录可能有所不同。  

- 如果一个 DLL 丢失或损坏，请尝试将其替换，然后重新启动服务。  

  有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：  

- [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)
