---
title: 协议找到的协议处于禁用或过期的状态 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b524f423-1325-495c-9499-33101f6388fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7e4092b057b83caef252d63853ecf6791edbde
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014718"
---
# <a name="agreement-found-for-the-protocol-is-in-disabled-or-expired-state"></a>为协议找到的协议处于禁用或过期的状态
## <a name="details"></a>详细信息  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  产品名称   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 产品版本 |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    事件 ID     |                                           -                                            |
|  事件源   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    组件    |                                       EDI 引擎                                       |
|  符号名称  |                     AgreementResolutionAgreementDiasbledOrExpired                      |
|  消息正文   |      为协议找到{0}协议处于禁用或已过期状态。      |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 能够解析到某个协议，但它处于禁用或已过期状态。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请启用该协议。