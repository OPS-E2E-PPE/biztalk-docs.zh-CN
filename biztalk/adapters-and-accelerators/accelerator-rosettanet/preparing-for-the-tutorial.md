---
title: 在 BizTalk Server 中 RosettaNet Loopback 教程的先决条件 |Microsoft Docs
description: 单步执行 BizTalk Server 中的 RosettaNet 加速器 (BTARN) 的 Loopback 教程的先决条件
caps.latest.revision: 9
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 807aa4002f08c9cb9f40f2bc6dad216bc2d730a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282621"
---
# <a name="prepare-for-the-tutorial"></a><span data-ttu-id="cd409-103">准备此教程</span><span class="sxs-lookup"><span data-stu-id="cd409-103">Prepare for the tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd409-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="cd409-104">Prerequisites</span></span>
<span data-ttu-id="cd409-105">Loopback 教程开始： 前</span><span class="sxs-lookup"><span data-stu-id="cd409-105">Before starting the Loopback tutorial:</span></span>
  
-   <span data-ttu-id="cd409-106">[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)快捷键。</span><span class="sxs-lookup"><span data-stu-id="cd409-106">[Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md) the accelerator.</span></span> <span data-ttu-id="cd409-107">您可能需要将 btarnhttpreceive 虚拟目录添加到在 SharePoint 管理中心内 Windows SharePoint 管理的路径排除列表。</span><span class="sxs-lookup"><span data-stu-id="cd409-107">You may have to add the btarnhttpreceive virtual directory to the Windows SharePoint managed path exclusion list in SharePoint Central Administration.</span></span>  
  
-   <span data-ttu-id="cd409-108">确保 BizTalkServerIsolatedHost 和 BizTalkServerApplication 主机已**受信任验证**选项处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="cd409-108">Be sure the BizTalkServerIsolatedHost and BizTalkServerApplication hosts have the **Authentication trusted** option enabled.</span></span> <span data-ttu-id="cd409-109">若要验证，打开 BizTalk Server 管理控制台中，然后展开**主机**。</span><span class="sxs-lookup"><span data-stu-id="cd409-109">To verify, open the BizTalk Server Administration console, and expand **Hosts**.</span></span> <span data-ttu-id="cd409-110">右键单击该主机中，选择**属性**，并检查**受信任验证**如果未启用。</span><span class="sxs-lookup"><span data-stu-id="cd409-110">Right-click the host, select **Properties**, and check **Authentication Trusted** if it's not enabled.</span></span>  

    <span data-ttu-id="cd409-111">如果您有多个主机实例，则删除所有只保留一个主机实例。</span><span class="sxs-lookup"><span data-stu-id="cd409-111">If you have more than one host instance, then delete all but one host instance.</span></span> <span data-ttu-id="cd409-112">例如，删除 BizTalk Server 独立主机实例，并保留 BizTalkServerApplication 主机实例）。</span><span class="sxs-lookup"><span data-stu-id="cd409-112">For example, delete the BizTalk Server Isolated Host instance, and keep the BizTalkServerApplication host instance).</span></span> <span data-ttu-id="cd409-113">这使你可以选择**受信任验证**与关联的实例，并重新创建其他主机实例的主机上。</span><span class="sxs-lookup"><span data-stu-id="cd409-113">This lets you select **Authentication Trusted** on the host associated with that instance, and then re-create the additional host instances.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="cd409-114">下一步</span><span class="sxs-lookup"><span data-stu-id="cd409-114">Next step</span></span>
 [<span data-ttu-id="cd409-115">步骤 1：创建本组织</span><span class="sxs-lookup"><span data-stu-id="cd409-115">Step 1: Create the Home Organization</span></span>](step-1-create-the-home-organization.md)