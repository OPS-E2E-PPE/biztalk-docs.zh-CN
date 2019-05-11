---
title: 单一登录：Event 10594 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c2f70c563113b7b7473d86046f2ac78eec4ea4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397855"
---
# <a name="single-sign-on-event-10594"></a>单一登录：事件 10594
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  产品名称   |                                                                                 企业单一登录                                                                                  |
| 产品版本 |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    事件 ID     |                                                                                           10594                                                                                            |
|  事件源   |                                                                                           ENTSSO                                                                                           |
|    组件    |                                                                                            不可用                                                                                             |
|  符号名称  |                                                                              SSO_WARN_TICKET_VALIDATE_FAILED                                                                               |
|  消息正文   | 票证验证失败。 发件人名称必须匹配的票证 issuer.%r<br /><br /> 应用程序名称: %1 %r<br /><br /> 票证颁发者: %2 %r<br /><br /> 发件人姓名： %3 |
  
## <a name="explanation"></a>解释  
 为了使票证进行验证，必须匹配 （中的警告消息） 的票证颁发者和发件人姓名字段。 如果，但是，通过 BizTalk 不受信任主机发送邮件，发件人名称获取更改为 BizTalk 主机的名称不受信任，并且票证将无效。  
  
## <a name="user-action"></a>用户操作  
 如果使用企业单一登录，请确保，您的消息只流经受信任的 BizTalk 主机。 这将减少与消息中的数据被篡改的风险。  
  
 如果您完全理解的安全隐患，为你的方案，可以关闭此应用程序的验证。 请注意，验证是一个管理选项，可以关闭状态的系统或只需为此特定应用程序。