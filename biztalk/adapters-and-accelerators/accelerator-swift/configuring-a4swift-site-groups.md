---
title: 配置 A4SWIFT 站点组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f19db0461fc4dc5584fa0774ba0476e3ee471b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969766"
---
# <a name="configuring-a4swift-site-groups"></a><span data-ttu-id="1579e-102">配置 A4SWIFT 站点组</span><span class="sxs-lookup"><span data-stu-id="1579e-102">Configuring A4SWIFT Site Groups</span></span>
<span data-ttu-id="1579e-103">您需要创建相应的网站用户组，可以锁定消息修复和新提交配置过程中创建的文档库上的权限。</span><span class="sxs-lookup"><span data-stu-id="1579e-103">You need to create the corresponding site groups to lock down the permissions on the document libraries created during Message Repair and New Submission configuration.</span></span> <span data-ttu-id="1579e-104">若要执行此操作与在上一部分中的示例，A4SWIFT 管理员会转到 MRSR 站点并设置以下站点组：</span><span class="sxs-lookup"><span data-stu-id="1579e-104">To do so with the example in the preceding section, an A4SWIFT Administrator would go to the MRSR site and set up the following site groups:</span></span>  
  
- <span data-ttu-id="1579e-105">Payments_Creators</span><span class="sxs-lookup"><span data-stu-id="1579e-105">Payments_Creators</span></span>  
  
- <span data-ttu-id="1579e-106">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="1579e-106">Payments_Repairers</span></span>  
  
- <span data-ttu-id="1579e-107">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="1579e-107">Payments_Approvers</span></span>  
  
  <span data-ttu-id="1579e-108">对于每个站点组应应用以下权限：</span><span class="sxs-lookup"><span data-stu-id="1579e-108">For each of these site groups the following permissions should be applied:</span></span>  
  
- <span data-ttu-id="1579e-109">**查看项。**</span><span class="sxs-lookup"><span data-stu-id="1579e-109">**View Items.**</span></span> <span data-ttu-id="1579e-110">查看列表、 文档库中的文档中的项，查看 Web 讨论评论，并设置列表的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1579e-110">View items in lists, documents in document libraries, view Web discussion comments, and set up e-mail alerts for lists.</span></span>  
  
- <span data-ttu-id="1579e-111">**视图页。**</span><span class="sxs-lookup"><span data-stu-id="1579e-111">**View Pages.**</span></span> <span data-ttu-id="1579e-112">查看 Web 站点中的页面。</span><span class="sxs-lookup"><span data-stu-id="1579e-112">View pages in a Web site.</span></span>  
  
  <span data-ttu-id="1579e-113">需要为每个用户都参与付款部门的角色，以创建新的站点用户并为该用户分配到站点组对应于[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MMC 配置期间创建的角色。</span><span class="sxs-lookup"><span data-stu-id="1579e-113">For each user who participates in the roles for the Payments department, you need to create a new site user and assign that user to the site group that corresponds to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] roles created during MMC configuration.</span></span>