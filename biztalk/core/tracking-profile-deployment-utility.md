---
title: "跟踪配置文件部署实用工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c4d261069b83741413e255a3f8bacd6dd9260d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-profile-deployment-utility"></a><span data-ttu-id="79101-102">跟踪配置文件部署实用工具</span><span class="sxs-lookup"><span data-stu-id="79101-102">Tracking Profile Deployment Utility</span></span>
<span data-ttu-id="79101-103">开发人员使用 bttdeploy 实用程序可以将跟踪配置文件应用于 BAM 基础结构，也可以用它从 BAM 基础结构中删除跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="79101-103">Developers use the bttdeploy utility to apply tracking profiles to and remove them from the BAM infrastructure.</span></span> <span data-ttu-id="79101-104">使用 bttdeploy 实用程序在功能上与单击跟踪配置文件编辑器 (TPE) 中的“应用跟踪配置文件”菜单选项一样。</span><span class="sxs-lookup"><span data-stu-id="79101-104">Using the bttdeploy utility is functionally equivalent to clicking the Apply Tracking Profile menu option in the Tracking Profile Editor (TPE).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79101-105">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="79101-105">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="79101-106">**用法**</span><span class="sxs-lookup"><span data-stu-id="79101-106">**Usage**</span></span>  
  
 <span data-ttu-id="79101-107">**bttdeploy.exe [选项] 文件名称**</span><span class="sxs-lookup"><span data-stu-id="79101-107">**bttdeploy.exe [options] file name**</span></span>  
  
|<span data-ttu-id="79101-108">选项</span><span class="sxs-lookup"><span data-stu-id="79101-108">Option</span></span>|<span data-ttu-id="79101-109">Description</span><span class="sxs-lookup"><span data-stu-id="79101-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="79101-110">/h 或 /?</span><span class="sxs-lookup"><span data-stu-id="79101-110">/h or /?</span></span>|<span data-ttu-id="79101-111">可选：显示 bttdeploy 的语法摘要。</span><span class="sxs-lookup"><span data-stu-id="79101-111">Optional: Displays the syntax summary for bttdeploy.</span></span>|  
|<span data-ttu-id="79101-112">/mgdb\<服务器名称 [，端口] >\\< 数据库名称\></span><span class="sxs-lookup"><span data-stu-id="79101-112">/mgdb \<server name[,port]>\\<database name\></span></span>|<span data-ttu-id="79101-113">可选：指定要将配置文件应用到的管理服务器、端口和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="79101-113">Optional: Specifies the management server, port, and database name to which to apply the profile.</span></span> <span data-ttu-id="79101-114">**注意：**端口使用此参数时，是可选的。</span><span class="sxs-lookup"><span data-stu-id="79101-114">**Note:**  When using this parameter, the port is optional.</span></span>|  
|<span data-ttu-id="79101-115">/remove</span><span class="sxs-lookup"><span data-stu-id="79101-115">/remove</span></span>|<span data-ttu-id="79101-116">可选：指定将从 BAM 数据库中删除跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="79101-116">Optional: Specifies that the tracking profile is to be removed from the BAM database.</span></span>|  
|<span data-ttu-id="79101-117">filename</span><span class="sxs-lookup"><span data-stu-id="79101-117">filename</span></span>|<span data-ttu-id="79101-118">要应用或删除的跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="79101-118">The name of the tracking profile file to apply or remove.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79101-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79101-119">See Also</span></span>  
 <span data-ttu-id="79101-120">[跟踪配置文件编辑器](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="79101-120">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="79101-121">如何删除孤立的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="79101-121">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)