---
title: 颁发和兑换单一登录票证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a0323a6-cc31-460d-b64d-b4d8142c3855
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04399b37fb977179afd668ec4aacc7e8c6aa5b7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329715"
---
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a>颁发和兑换单一登录票证
链接用户和关联应用程序后，可以颁发票证以帮助确保安全，同时保持通信。 单一登录票证的工作方式与其他票证颁发技术： 之前关闭发送消息，追加上单一登录票证作为字符串消息。 服务器接收消息，对票证进行解码并根据需要使用的信息。  
  
### <a name="to-issue-a-single-sign-on-ticket"></a>若要颁发单一登录票证  
  
1.  创建新的票证对象通过调用我`SSOTicket`。  
  
2.  通过调用我颁发票证`SSOTicket.IssueTicket`。  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a>若要兑换单一登录票证  
  
1.  创建新的票证对象通过调用我`SSOTicket`。  
  
2.  通过调用我的票证兑换`SSOTicket.RedeemTicket`。  
  
## <a name="see-also"></a>请参阅  
 [使用企业单一登录编程](../core/programming-with-enterprise-single-sign-on.md)