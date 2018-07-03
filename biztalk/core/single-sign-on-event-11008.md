---
title: 单一登录： 事件 11008 |Microsoft Docs
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
ms.openlocfilehash: 7f3a77dcfb89a3040cf6c1acb71a053d57393591
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983726"
---
# <a name="single-sign-on-event-11008"></a>单一登录： 事件 11008
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                 企业单一登录                                                                 |
| 产品版本 |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    事件 ID     |                                                                           11008                                                                           |
|  事件源   |                                                                          ENTSSO                                                                           |
|    组件    |                                                                            N/A                                                                            |
|  符号名称  |                                                                   SSO_WARN_CHECK_GROUP                                                                    |
|  消息正文   | 检查组成员失败。%r<br /><br /> 组名称: %1 %r<br /><br /> 帐户名称: %2 %r<br /><br /> 其他数据: %3 %r<br /><br /> 错误代码： %4 |
  
## <a name="explanation"></a>解释  
 引起此问题的主要原因可能是网络问题、跨域使用或混合使用不同级别的域控制器（例如，您的系统使用来自 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 和 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的域控制器）。  
  
## <a name="user-action"></a>用户操作  
 请与网络管理员核对以查看是否存在任何网络问题，或您的系统是否存在跨域使用或混合使用不同级别的域控制器。