---
title: 单一登录：Event 11070 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1382d436528f630ec4abb51af98599371d69a297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243524"
---
# <a name="single-sign-on-event-11070"></a>单一登录：事件 11070
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                               企业单一登录                                                                                               |
| 产品版本 |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    事件 ID     |                                                                                                         11070                                                                                                         |
|  事件源   |                                                                                                        ENTSSO                                                                                                         |
|    组件    |                                                                                                          不可用                                                                                                          |
|  符号名称  |                                                                                             SSO_WARN_PS_MIIS_NOT_ALLOWED                                                                                              |
|  消息正文   | 此 SSO 服务器当前未配置为允许从 MIIS 执行 Windows 密码更改。 使用 ssoconfig-allowPS MIIS yes 或 SSO 管理 MMC.%r<br /><br /> 跟踪 ID: %1 %r<br /><br /> 客户端用户： %2 |
  
## <a name="explanation"></a>解释  
 此 SSO 服务器当前未配置为允许从 MIIS 执行 Windows 密码更改。  
  
## <a name="user-action"></a>用户操作  
 若要允许从 MIIS 中的 Windows 密码更改**服务器管理单元**，**密码同步属性**选项卡上，选择**允许从 MIIS 进行密码同步。**  
  
 有关详细信息，请参阅[如何使用服务器管理单元中](../core/how-to-use-the-servers-snap-in.md)。