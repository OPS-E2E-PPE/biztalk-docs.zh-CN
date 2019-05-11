---
title: 单一登录：事件 11069 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc680a452c6e70f6e10623779da1ca312f62a1fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396080"
---
# <a name="single-sign-on-event-11069"></a>单一登录：事件 11069
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                               企业单一登录                                                                                               |
| 产品版本 |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                         11069                                                                                                         |
|  事件源   |                                                                                                        ENTSSO                                                                                                         |
|    组件    |                                                                                                          不可用                                                                                                          |
|  符号名称  |                                                                                             SSO_WARN_PS_PCNS_NOT_ALLOWED                                                                                              |
|  消息正文   | 此 SSO 服务器当前未配置为允许从 PCNS 进行 Windows 密码更改。 使用 ssoconfig-allowPS PCNS yes 或 SSO 管理 MMC.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户： %2 |
  
## <a name="explanation"></a>解释  
 此 SSO 服务器当前未配置为允许从 PCNS 进行 Windows 密码更改。  
  
## <a name="user-action"></a>用户操作  
 若要允许从 PCNS，Windows 密码更改，在**服务器管理单元**，**密码同步属性**选项卡上，选择**允许从 PCNS 进行密码同步。**  
  
 有关详细信息，请参阅[如何使用服务器管理单元中](../core/how-to-use-the-servers-snap-in.md)。