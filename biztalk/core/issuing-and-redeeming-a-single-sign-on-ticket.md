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
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a><span data-ttu-id="61e6d-102">颁发和兑换单一登录票证</span><span class="sxs-lookup"><span data-stu-id="61e6d-102">Issuing and Redeeming a Single Sign-On Ticket</span></span>
<span data-ttu-id="61e6d-103">在将用户和关联应用程序链接到一起之后，可以颁发票证以帮助确保在维持通信的同时保证安全性。</span><span class="sxs-lookup"><span data-stu-id="61e6d-103">After you link a user and an affiliate application, you can issue tickets to help ensure security while maintaining communications.</span></span> <span data-ttu-id="61e6d-104">单一登录票证的工作方式与其他票证技术： 发送消息之前, 追加上单一登录票证到作为字符串消息。</span><span class="sxs-lookup"><span data-stu-id="61e6d-104">Single Sign-On ticketing works just like other ticketing technologies: before sending the message off, you append the Single Sign-On ticket to the message as a string.</span></span> <span data-ttu-id="61e6d-105">服务器接收消息，对票证进行解码，然后根据需要使用信息。</span><span class="sxs-lookup"><span data-stu-id="61e6d-105">The server receives your message, decodes the ticket, and uses the information as appropriate.</span></span>  
  
### <a name="to-issue-a-single-sign-on-ticket"></a><span data-ttu-id="61e6d-106">若要发出的单一登录票证</span><span class="sxs-lookup"><span data-stu-id="61e6d-106">To issue a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="61e6d-107">通过调用 I`SSOTicket` 创建新的票证对象。</span><span class="sxs-lookup"><span data-stu-id="61e6d-107">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="61e6d-108">通过调用 I`SSOTicket.IssueTicket` 颁发票证。</span><span class="sxs-lookup"><span data-stu-id="61e6d-108">Issue the ticket with a call to I`SSOTicket.IssueTicket`.</span></span>  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a><span data-ttu-id="61e6d-109">若要兑换上单一登录票证</span><span class="sxs-lookup"><span data-stu-id="61e6d-109">To redeem a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="61e6d-110">通过调用 I`SSOTicket` 创建新的票证对象。</span><span class="sxs-lookup"><span data-stu-id="61e6d-110">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="61e6d-111">通过调用 I`SSOTicket.RedeemTicket` 兑换票证。</span><span class="sxs-lookup"><span data-stu-id="61e6d-111">Redeem the ticket with a call to I`SSOTicket.RedeemTicket`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e6d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61e6d-112">See Also</span></span>  
 [<span data-ttu-id="61e6d-113">使用企业单一登录进行编程</span><span class="sxs-lookup"><span data-stu-id="61e6d-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)