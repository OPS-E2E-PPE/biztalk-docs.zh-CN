---
title: 配置 A4SWIFT 用户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b75a3e95c836f8a577543b43319e6abe49a96c42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005254"
---
# <a name="configuring-a4swift-users"></a><span data-ttu-id="44fcc-102">配置 A4SWIFT 用户</span><span class="sxs-lookup"><span data-stu-id="44fcc-102">Configuring A4SWIFT Users</span></span>
<span data-ttu-id="44fcc-103">安装过程中的[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]，A4SWIFT 配置程序创建默认贸易合作伙伴配置文件和协议，并将注册 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="44fcc-103">During installation of [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)], the A4SWIFT configuration program creates default trading partner profiles and agreements, and registers the BizTalk Server.</span></span> <span data-ttu-id="44fcc-104">A4SWIFT 还会创建消息修复和新提交组件使用的文档库。</span><span class="sxs-lookup"><span data-stu-id="44fcc-104">A4SWIFT also creates document libraries used by the Message Repair and New Submission component.</span></span>  
  
 <span data-ttu-id="44fcc-105">A4SWIFT 安装过程中创建以下文档文件夹：</span><span class="sxs-lookup"><span data-stu-id="44fcc-105">A4SWIFT creates the following document folders during installation:</span></span>  
  
- <span data-ttu-id="44fcc-106">发件箱文档库</span><span class="sxs-lookup"><span data-stu-id="44fcc-106">Outbox document library</span></span>  
  
- <span data-ttu-id="44fcc-107">模板文档库</span><span class="sxs-lookup"><span data-stu-id="44fcc-107">Templates document library</span></span>  
  
- <span data-ttu-id="44fcc-108">未分析的文档库</span><span class="sxs-lookup"><span data-stu-id="44fcc-108">Unparsed document library</span></span>  
  
- <span data-ttu-id="44fcc-109">新 SWIFT MT 消息文档库</span><span class="sxs-lookup"><span data-stu-id="44fcc-109">New SWIFT MT Message document library</span></span>  
  
- <span data-ttu-id="44fcc-110">新 SWIFT MX 消息文档库</span><span class="sxs-lookup"><span data-stu-id="44fcc-110">New SWIFT MX Messages document library</span></span>  
  
  <span data-ttu-id="44fcc-111">每个部门创建，A4SWIFT 管理员必须手动设置了相应的部门的站点组和 A4SWIFT 定义的角色。</span><span class="sxs-lookup"><span data-stu-id="44fcc-111">For each department created, the A4SWIFT Administrator must manually set up site groups for the corresponding departments and A4SWIFT defined roles.</span></span> <span data-ttu-id="44fcc-112">每个部门/角色具有自动创建的配置文件 Web Client(PWC) 收件箱。</span><span class="sxs-lookup"><span data-stu-id="44fcc-112">Each department/role has an inbox created automatically by the Profile Web Client(PWC).</span></span>  
  
  <span data-ttu-id="44fcc-113">A4SWIFT 安装配置程序完成后，A4SWIFT 管理员在组织中配置的每个部门的工作流。</span><span class="sxs-lookup"><span data-stu-id="44fcc-113">After the A4SWIFT setup configuration program is completed, the A4SWIFT Administrator configures workflows for each department in the organization.</span></span> <span data-ttu-id="44fcc-114">消息修复和新提交在配置期间，通过配置文件 Web 客户端，为每个部门/角色组合创建相应的收件箱。</span><span class="sxs-lookup"><span data-stu-id="44fcc-114">During Message Repair and New Submission configuration, through the Profile Web Client, corresponding inboxes are created for each department/role combination.</span></span> <span data-ttu-id="44fcc-115">例如，在 PWC 配置期间 A4SWIFT 管理员创建名为付款的部门，然后将的创建者、 Repairers 和审批者角色分配到名为付款的部门。</span><span class="sxs-lookup"><span data-stu-id="44fcc-115">For example, during PWC configuration an A4SWIFT Administrator creates a department named Payments and then assigns the roles of Creators, Repairers, and Approvers to a department called Payments.</span></span> <span data-ttu-id="44fcc-116">MRSR 站点上的文档库创建收件箱名称在下表中的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="44fcc-116">Document libraries on the MRSR site are created with the inbox names as shown in the examples in the following table:</span></span>  
  
|<span data-ttu-id="44fcc-117">部门名称</span><span class="sxs-lookup"><span data-stu-id="44fcc-117">Department name</span></span>|<span data-ttu-id="44fcc-118">角色名称</span><span class="sxs-lookup"><span data-stu-id="44fcc-118">Role name</span></span>|<span data-ttu-id="44fcc-119">收件箱名称</span><span class="sxs-lookup"><span data-stu-id="44fcc-119">Inbox name</span></span>|  
|---------------------|---------------|----------------|  
|<span data-ttu-id="44fcc-120">支付</span><span class="sxs-lookup"><span data-stu-id="44fcc-120">Payments</span></span>|<span data-ttu-id="44fcc-121">创建者</span><span class="sxs-lookup"><span data-stu-id="44fcc-121">Creators</span></span>|<span data-ttu-id="44fcc-122">Payments_Creator</span><span class="sxs-lookup"><span data-stu-id="44fcc-122">Payments_Creator</span></span>|  
|<span data-ttu-id="44fcc-123">支付</span><span class="sxs-lookup"><span data-stu-id="44fcc-123">Payments</span></span>|<span data-ttu-id="44fcc-124">Repairers</span><span class="sxs-lookup"><span data-stu-id="44fcc-124">Repairers</span></span>|<span data-ttu-id="44fcc-125">Payments_Repairers</span><span class="sxs-lookup"><span data-stu-id="44fcc-125">Payments_Repairers</span></span>|  
|<span data-ttu-id="44fcc-126">支付</span><span class="sxs-lookup"><span data-stu-id="44fcc-126">Payments</span></span>|<span data-ttu-id="44fcc-127">审批者</span><span class="sxs-lookup"><span data-stu-id="44fcc-127">Approvers</span></span>|<span data-ttu-id="44fcc-128">Payments_Approvers</span><span class="sxs-lookup"><span data-stu-id="44fcc-128">Payments_Approvers</span></span>|