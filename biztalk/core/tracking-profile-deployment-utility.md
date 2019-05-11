---
title: 跟踪配置文件部署实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d631b7c-a40f-4cee-88a4-3d932ab7fde0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf72709c0527b9bc39b238be6d2ca98b698530fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313801"
---
# <a name="tracking-profile-deployment-utility"></a><span data-ttu-id="09b81-102">跟踪配置文件部署实用程序</span><span class="sxs-lookup"><span data-stu-id="09b81-102">Tracking Profile Deployment Utility</span></span>
<span data-ttu-id="09b81-103">开发人员使用 bttdeploy 实用程序应用到的跟踪配置文件，并从 BAM 基础结构中删除它们。</span><span class="sxs-lookup"><span data-stu-id="09b81-103">Developers use the bttdeploy utility to apply tracking profiles to and remove them from the BAM infrastructure.</span></span> <span data-ttu-id="09b81-104">使用 bttdeploy 实用程序在功能上等效于单击应用跟踪配置文件菜单选项在跟踪配置文件编辑器 (TPE)。</span><span class="sxs-lookup"><span data-stu-id="09b81-104">Using the bttdeploy utility is functionally equivalent to clicking the Apply Tracking Profile menu option in the Tracking Profile Editor (TPE).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09b81-105">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="09b81-105">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
 <span data-ttu-id="09b81-106">**Usage**</span><span class="sxs-lookup"><span data-stu-id="09b81-106">**Usage**</span></span>  
  
 <span data-ttu-id="09b81-107">**bttdeploy.exe [options] file name**</span><span class="sxs-lookup"><span data-stu-id="09b81-107">**bttdeploy.exe [options] file name**</span></span>  
  
|<span data-ttu-id="09b81-108">Option</span><span class="sxs-lookup"><span data-stu-id="09b81-108">Option</span></span>|<span data-ttu-id="09b81-109">Description</span><span class="sxs-lookup"><span data-stu-id="09b81-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="09b81-110">/h 或 /？</span><span class="sxs-lookup"><span data-stu-id="09b81-110">/h or /?</span></span>|<span data-ttu-id="09b81-111">可选：显示摘要 bttdeploy 的语法。</span><span class="sxs-lookup"><span data-stu-id="09b81-111">Optional: Displays the syntax summary for bttdeploy.</span></span>|  
|<span data-ttu-id="09b81-112">/mgdb \<server name[,port]\>\\<database name\></span><span class="sxs-lookup"><span data-stu-id="09b81-112">/mgdb \<server name[,port]\>\\<database name\></span></span>|<span data-ttu-id="09b81-113">可选：指定管理服务器、 端口和要对其应用该配置文件的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="09b81-113">Optional: Specifies the management server, port, and database name to which to apply the profile.</span></span> <span data-ttu-id="09b81-114">**注意：** 使用此参数时，该端口是可选的。</span><span class="sxs-lookup"><span data-stu-id="09b81-114">**Note:**  When using this parameter, the port is optional.</span></span>|  
|<span data-ttu-id="09b81-115">/remove</span><span class="sxs-lookup"><span data-stu-id="09b81-115">/remove</span></span>|<span data-ttu-id="09b81-116">可选：指定跟踪配置文件将从 BAM 数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="09b81-116">Optional: Specifies that the tracking profile is to be removed from the BAM database.</span></span>|  
|<span data-ttu-id="09b81-117">filename</span><span class="sxs-lookup"><span data-stu-id="09b81-117">filename</span></span>|<span data-ttu-id="09b81-118">跟踪的名称配置可应用或删除的文件。</span><span class="sxs-lookup"><span data-stu-id="09b81-118">The name of the tracking profile file to apply or remove.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09b81-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="09b81-119">See Also</span></span>  
 <span data-ttu-id="09b81-120">[跟踪配置文件编辑器](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="09b81-120">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 [<span data-ttu-id="09b81-121">如何删除孤立的跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="09b81-121">How to Remove Orphaned Tracking Profiles</span></span>](../core/how-to-remove-orphaned-tracking-profiles.md)