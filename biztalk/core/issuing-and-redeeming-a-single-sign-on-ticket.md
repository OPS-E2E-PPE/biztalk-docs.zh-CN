---
title: "颁发和兑换单一登录票证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0323a6-cc31-460d-b64d-b4d8142c3855
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9988eedb545b3b1a348a5de6275b176abe2be7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a>颁发和兑换单一登录票证
在将用户和关联应用程序链接到一起之后，可以颁发票证以帮助确保在维持通信的同时保证安全性。 单一登录票证的工作方式与其他票证技术： 发送消息之前, 追加上单一登录票证到作为字符串消息。 服务器接收消息，对票证进行解码，然后根据需要使用信息。  
  
### <a name="to-issue-a-single-sign-on-ticket"></a>若要发出的单一登录票证  
  
1.  通过调用 I`SSOTicket` 创建新的票证对象。  
  
2.  通过调用 I`SSOTicket.IssueTicket` 颁发票证。  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a>若要兑换上单一登录票证  
  
1.  通过调用 I`SSOTicket` 创建新的票证对象。  
  
2.  通过调用 I`SSOTicket.RedeemTicket` 兑换票证。  
  
## <a name="see-also"></a>另请参阅  
 [使用企业单一登录进行编程](../core/programming-with-enterprise-single-sign-on.md)