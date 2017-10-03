---
title: "BizTalk Server 权限的疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e47bd1fc-2edf-4525-97dd-4bd9d3e2d6ff
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb280141b6817a622c84c16a3b66df289472cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-permissions"></a><span data-ttu-id="047d6-102">BizTalk Server 权限的疑难解答</span><span class="sxs-lookup"><span data-stu-id="047d6-102">Troubleshooting BizTalk Server Permissions</span></span>
<span data-ttu-id="047d6-103">BizTalk Server 中存在的权限问题通常属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="047d6-103">Permissions problems in BizTalk Server typically fall into one of the following categories:</span></span>  
  
-   <span data-ttu-id="047d6-104">SQL Server 权限</span><span class="sxs-lookup"><span data-stu-id="047d6-104">SQL Server permissions</span></span>  
  
-   <span data-ttu-id="047d6-105">多服务器 BizTalk Server 安装中的 Active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="047d6-105">Active Directory permissions on multiserver installations of BizTalk Server</span></span>  
  
-   <span data-ttu-id="047d6-106">Web Services 权限</span><span class="sxs-lookup"><span data-stu-id="047d6-106">Web services permissions</span></span>  
  
-   <span data-ttu-id="047d6-107">IIS 权限</span><span class="sxs-lookup"><span data-stu-id="047d6-107">IIS permissions</span></span>  
  
 <span data-ttu-id="047d6-108">本主题提供了避免出现权限问题的一些通用准则，并介绍了针对特定方案的疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="047d6-108">This topic provides some general guidelines for avoiding permissions problems and troubleshooting steps for specific scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="047d6-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="047d6-109">In This Section</span></span>  
  
-   [<span data-ttu-id="047d6-110">解决 SQL Server 的权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="047d6-110">Guidelines for Resolving SQL Server Permissions Problems</span></span>](../core/guidelines-for-resolving-sql-server-permissions-problems.md)  
  
-   [<span data-ttu-id="047d6-111">准则用于实现在多服务器 BizTalk 安装上的 Active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="047d6-111">Guidelines for Implementing Active Directory Permissions on Multi Server BizTalk Installations</span></span>](../core/implement-active-directory-permissions-on-multi-server-biztalk-installations.md)  
  
-   [<span data-ttu-id="047d6-112">解决 Web 服务的权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="047d6-112">Guidelines for Resolving Web Services Permissions Problems</span></span>](../core/guidelines-for-resolving-web-services-permissions-problems.md)  
  
-   [<span data-ttu-id="047d6-113">以解决 IIS 权限问题的指导原则</span><span class="sxs-lookup"><span data-stu-id="047d6-113">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)