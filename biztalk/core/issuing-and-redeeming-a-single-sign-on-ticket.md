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
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a><span data-ttu-id="5015d-102">颁发和兑换单一登录票证</span><span class="sxs-lookup"><span data-stu-id="5015d-102">Issuing and Redeeming a Single Sign-On Ticket</span></span>
<span data-ttu-id="5015d-103">链接用户和关联应用程序后，可以颁发票证以帮助确保安全，同时保持通信。</span><span class="sxs-lookup"><span data-stu-id="5015d-103">After you link a user and an affiliate application, you can issue tickets to help ensure security while maintaining communications.</span></span> <span data-ttu-id="5015d-104">单一登录票证的工作方式与其他票证颁发技术： 之前关闭发送消息，追加上单一登录票证作为字符串消息。</span><span class="sxs-lookup"><span data-stu-id="5015d-104">Single Sign-On ticketing works just like other ticketing technologies: before sending the message off, you append the Single Sign-On ticket to the message as a string.</span></span> <span data-ttu-id="5015d-105">服务器接收消息，对票证进行解码并根据需要使用的信息。</span><span class="sxs-lookup"><span data-stu-id="5015d-105">The server receives your message, decodes the ticket, and uses the information as appropriate.</span></span>  
  
### <a name="to-issue-a-single-sign-on-ticket"></a><span data-ttu-id="5015d-106">若要颁发单一登录票证</span><span class="sxs-lookup"><span data-stu-id="5015d-106">To issue a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="5015d-107">创建新的票证对象通过调用我`SSOTicket`。</span><span class="sxs-lookup"><span data-stu-id="5015d-107">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="5015d-108">通过调用我颁发票证`SSOTicket.IssueTicket`。</span><span class="sxs-lookup"><span data-stu-id="5015d-108">Issue the ticket with a call to I`SSOTicket.IssueTicket`.</span></span>  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a><span data-ttu-id="5015d-109">若要兑换单一登录票证</span><span class="sxs-lookup"><span data-stu-id="5015d-109">To redeem a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="5015d-110">创建新的票证对象通过调用我`SSOTicket`。</span><span class="sxs-lookup"><span data-stu-id="5015d-110">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="5015d-111">通过调用我的票证兑换`SSOTicket.RedeemTicket`。</span><span class="sxs-lookup"><span data-stu-id="5015d-111">Redeem the ticket with a call to I`SSOTicket.RedeemTicket`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5015d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5015d-112">See Also</span></span>  
 [<span data-ttu-id="5015d-113">使用企业单一登录编程</span><span class="sxs-lookup"><span data-stu-id="5015d-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)