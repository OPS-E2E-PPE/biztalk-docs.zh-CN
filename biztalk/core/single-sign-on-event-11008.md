---
title: 单一登录：事件 11008 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 367bb91906d659f0848e1745796c639d5e08f0b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306657"
---
# <a name="single-sign-on-event-11008"></a>单一登录：事件 11008
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                 企业单一登录                                                                 |
| 产品版本 |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    事件 ID     |                                                                           11008                                                                           |
|  事件源   |                                                                          ENTSSO                                                                           |
|    组件    |                                                                            不可用                                                                            |
|  符号名称  |                                                                   SSO_WARN_CHECK_GROUP                                                                    |
|  消息正文   | 检查组成员身份 failed.%r<br /><br /> 组名称: %1 %r<br /><br /> 帐户名称: %2 %r<br /><br /> 其他数据: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 这很可能是因网络问题、 跨域使用或混合的级别的域控制器 (例如，如果您的系统使用从这两个域控制器[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]和[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)])。  
  
## <a name="user-action"></a>用户操作  
 请与网络管理员联系，以查看是否有任何网络问题，或您的系统具有任何跨域使用或混合的级别的域控制器。