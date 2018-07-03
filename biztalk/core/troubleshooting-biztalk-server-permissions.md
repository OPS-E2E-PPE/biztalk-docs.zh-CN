---
title: BizTalk Server 权限的疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e47bd1fc-2edf-4525-97dd-4bd9d3e2d6ff
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c4187d666cb0f93229a0cf4117ca24b92d479c9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995990"
---
# <a name="troubleshooting-biztalk-server-permissions"></a><span data-ttu-id="a5b48-102">故障排除的 BizTalk Server 权限</span><span class="sxs-lookup"><span data-stu-id="a5b48-102">Troubleshooting BizTalk Server Permissions</span></span>
<span data-ttu-id="a5b48-103">BizTalk Server 中存在的权限问题通常属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="a5b48-103">Permissions problems in BizTalk Server typically fall into one of the following categories:</span></span>  
  
- <span data-ttu-id="a5b48-104">SQL Server 权限</span><span class="sxs-lookup"><span data-stu-id="a5b48-104">SQL Server permissions</span></span>  
  
- <span data-ttu-id="a5b48-105">多服务器 BizTalk Server 安装中的 Active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="a5b48-105">Active Directory permissions on multiserver installations of BizTalk Server</span></span>  
  
- <span data-ttu-id="a5b48-106">Web Services 权限</span><span class="sxs-lookup"><span data-stu-id="a5b48-106">Web services permissions</span></span>  
  
- <span data-ttu-id="a5b48-107">IIS 权限</span><span class="sxs-lookup"><span data-stu-id="a5b48-107">IIS permissions</span></span>  
  
  <span data-ttu-id="a5b48-108">本主题提供了避免出现权限问题的一些通用准则，并介绍了针对特定方案的疑难解答步骤。</span><span class="sxs-lookup"><span data-stu-id="a5b48-108">This topic provides some general guidelines for avoiding permissions problems and troubleshooting steps for specific scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5b48-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="a5b48-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a5b48-110">解决 SQL Server 权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="a5b48-110">Guidelines for Resolving SQL Server Permissions Problems</span></span>](../core/guidelines-for-resolving-sql-server-permissions-problems.md)  
  
-   [<span data-ttu-id="a5b48-111">准则用于实现在多服务器 BizTalk 安装在 Active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="a5b48-111">Guidelines for Implementing Active Directory Permissions on Multi Server BizTalk Installations</span></span>](../core/implement-active-directory-permissions-on-multi-server-biztalk-installations.md)  
  
-   [<span data-ttu-id="a5b48-112">解决 Web Services 权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="a5b48-112">Guidelines for Resolving Web Services Permissions Problems</span></span>](../core/guidelines-for-resolving-web-services-permissions-problems.md)  
  
-   [<span data-ttu-id="a5b48-113">解决 IIS 权限疑难问题的准则</span><span class="sxs-lookup"><span data-stu-id="a5b48-113">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)