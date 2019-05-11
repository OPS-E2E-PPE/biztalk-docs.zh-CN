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
ms.openlocfilehash: f8996bac83803917c3fb3fd5b209d5cbfa73ff75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292941"
---
# <a name="troubleshooting-biztalk-server-permissions"></a><span data-ttu-id="45b55-102">故障排除的 BizTalk Server 权限</span><span class="sxs-lookup"><span data-stu-id="45b55-102">Troubleshooting BizTalk Server Permissions</span></span>
<span data-ttu-id="45b55-103">在 BizTalk Server 中的权限问题通常属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="45b55-103">Permissions problems in BizTalk Server typically fall into one of the following categories:</span></span>  
  
- <span data-ttu-id="45b55-104">SQL Server 权限</span><span class="sxs-lookup"><span data-stu-id="45b55-104">SQL Server permissions</span></span>  
  
- <span data-ttu-id="45b55-105">在 BizTalk Server 的多服务器安装的 active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="45b55-105">Active Directory permissions on multiserver installations of BizTalk Server</span></span>  
  
- <span data-ttu-id="45b55-106">Web services 权限</span><span class="sxs-lookup"><span data-stu-id="45b55-106">Web services permissions</span></span>  
  
- <span data-ttu-id="45b55-107">IIS 权限</span><span class="sxs-lookup"><span data-stu-id="45b55-107">IIS permissions</span></span>  
  
  <span data-ttu-id="45b55-108">本主题提供了避免出现权限问题和故障排除步骤适用于特定方案的一些通用准则。</span><span class="sxs-lookup"><span data-stu-id="45b55-108">This topic provides some general guidelines for avoiding permissions problems and troubleshooting steps for specific scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45b55-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="45b55-109">In This Section</span></span>  
  
-   [<span data-ttu-id="45b55-110">解决 SQL Server 权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="45b55-110">Guidelines for Resolving SQL Server Permissions Problems</span></span>](../core/guidelines-for-resolving-sql-server-permissions-problems.md)  
  
-   [<span data-ttu-id="45b55-111">准则用于实现在多服务器 BizTalk 安装在 Active Directory 权限</span><span class="sxs-lookup"><span data-stu-id="45b55-111">Guidelines for Implementing Active Directory Permissions on Multi Server BizTalk Installations</span></span>](../core/implement-active-directory-permissions-on-multi-server-biztalk-installations.md)  
  
-   [<span data-ttu-id="45b55-112">解决 Web Services 权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="45b55-112">Guidelines for Resolving Web Services Permissions Problems</span></span>](../core/guidelines-for-resolving-web-services-permissions-problems.md)  
  
-   [<span data-ttu-id="45b55-113">解决 IIS 权限疑难问题的准则</span><span class="sxs-lookup"><span data-stu-id="45b55-113">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)