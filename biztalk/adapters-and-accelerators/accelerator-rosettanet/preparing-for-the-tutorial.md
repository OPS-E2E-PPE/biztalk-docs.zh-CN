---
title: BizTalk Server 中的 RosettaNet 环回教程的先决条件 |Microsoft 文档
description: 单步执行 RosettaNet 快捷键 (BTARN) BizTalk Server 中的环回本教程的先决条件
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
ms.openlocfilehash: 9767f7823e80d4de67345ba0fbf59c1435adb8e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206957"
---
# <a name="prepare-for-the-tutorial"></a><span data-ttu-id="44c6b-103">准备教程</span><span class="sxs-lookup"><span data-stu-id="44c6b-103">Prepare for the tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44c6b-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="44c6b-104">Prerequisites</span></span>
<span data-ttu-id="44c6b-105">之前开始环回教程：</span><span class="sxs-lookup"><span data-stu-id="44c6b-105">Before starting the Loopback tutorial:</span></span>
  
-   <span data-ttu-id="44c6b-106">[安装和配置](install-configure-biztalk-accelerator-for-rosettanet.md)快捷键。</span><span class="sxs-lookup"><span data-stu-id="44c6b-106">[Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md) the accelerator.</span></span> <span data-ttu-id="44c6b-107">你可能需要将 btarnhttpreceive 虚拟目录添加到在 SharePoint 管理中心内的 Windows SharePoint 托管的路径排除列表。</span><span class="sxs-lookup"><span data-stu-id="44c6b-107">You may have to add the btarnhttpreceive virtual directory to the Windows SharePoint managed path exclusion list in SharePoint Central Administration.</span></span>  
  
-   <span data-ttu-id="44c6b-108">必须确保 BizTalkServerIsolatedHost 和 BizTalkServerApplication 主机具有**受信任的身份验证**选项处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="44c6b-108">Be sure the BizTalkServerIsolatedHost and BizTalkServerApplication hosts have the **Authentication trusted** option enabled.</span></span> <span data-ttu-id="44c6b-109">若要验证，打开 BizTalk Server 管理控制台中，然后展开**主机**。</span><span class="sxs-lookup"><span data-stu-id="44c6b-109">To verify, open the BizTalk Server Administration console, and expand **Hosts**.</span></span> <span data-ttu-id="44c6b-110">右键单击主机，选择**属性**，并检查**受信任的身份验证**如果未启用。</span><span class="sxs-lookup"><span data-stu-id="44c6b-110">Right-click the host, select **Properties**, and check **Authentication Trusted** if it's not enabled.</span></span>  

    <span data-ttu-id="44c6b-111">如果你有多个主机实例，然后删除所有只保留一个主机实例。</span><span class="sxs-lookup"><span data-stu-id="44c6b-111">If you have more than one host instance, then delete all but one host instance.</span></span> <span data-ttu-id="44c6b-112">例如，删除 BizTalk Server 隔离的主机实例，并保留 BizTalkServerApplication 主机实例）。</span><span class="sxs-lookup"><span data-stu-id="44c6b-112">For example, delete the BizTalk Server Isolated Host instance, and keep the BizTalkServerApplication host instance).</span></span> <span data-ttu-id="44c6b-113">此允许你选择**受信任的身份验证**上与关联的主机的实例，然后重新创建额外的主机实例。</span><span class="sxs-lookup"><span data-stu-id="44c6b-113">This lets you select **Authentication Trusted** on the host associated with that instance, and then re-create the additional host instances.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="44c6b-114">下一步</span><span class="sxs-lookup"><span data-stu-id="44c6b-114">Next step</span></span>
 [<span data-ttu-id="44c6b-115">步骤 1： 创建主组织</span><span class="sxs-lookup"><span data-stu-id="44c6b-115">Step 1: Create the Home Organization</span></span>](step-1-create-the-home-organization.md)