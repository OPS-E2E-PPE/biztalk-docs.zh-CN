---
title: 单一登录：Event 10563 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b735a435a076b873b8462f3b794012f731956ad1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398810"
---
# <a name="single-sign-on-event-10563"></a>单一登录：事件 10563
## <a name="details"></a>详细信息  
  
|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  产品名称   |                      企业单一登录                       |
| 产品版本 |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    事件 ID     |                                10563                                 |
|  事件源   |                                ENTSSO                                |
|    组件    |                                 不可用                                  |
|  符号名称  |                       SSO_WARN_PERFMON_FAILED                        |
|  消息正文   | 性能监视无法 start.%r<br /><br /> 错误代码： %1 |
  
## <a name="explanation"></a>解释  
 性能监视启动失败。 系统将继续正常运行，但性能监视将不可用。  
  
## <a name="user-action"></a>用户操作  
 它可能需要卸载并重新安装 perfmon 实用程序。