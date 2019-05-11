---
title: 禁用 BAM 跟踪 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, disabling BAM tracking
- BAM tracking
ms.assetid: ea5fef0e-7a96-46f5-81d8-9b1d8a5d24d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70760db419ac11386e0cfa83b85b89fdd0bc63f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378047"
---
# <a name="disabling-bam-tracking"></a><span data-ttu-id="f9b8b-102">禁用 BAM 跟踪</span><span class="sxs-lookup"><span data-stu-id="f9b8b-102">Disabling BAM Tracking</span></span>
<span data-ttu-id="f9b8b-103">默认情况下为 FIN 响应对帐启用了 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-103">By default, BAM tracking is enabled for FIN Response Reconciliation.</span></span> <span data-ttu-id="f9b8b-104">可以禁用它，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-104">You can disable it as follows.</span></span>  
  
### <a name="to-disable-bam-tracking-for-frr"></a><span data-ttu-id="f9b8b-105">若要禁用 BAM 跟踪 FRR</span><span class="sxs-lookup"><span data-stu-id="f9b8b-105">To disable BAM tracking for FRR</span></span>  
  
1.  <span data-ttu-id="f9b8b-106">单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="f9b8b-107">在注册表编辑器的左窗格中，转到我的计算机/HKEY_LOCAL_MACHINE/软件/Microsoft/BizTalk Accelerator for SWIFT/FRR。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f9b8b-108">FIN 响应对帐运行在每台计算机上，必须修改此注册表项。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-108">This registry entry must be modified on each computer that FIN Response Reconciliation is running on.</span></span>  
  
3.  <span data-ttu-id="f9b8b-109">在注册表编辑器的右窗格中，双击**BAMTrackingEnabled**。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-109">In the right pane of the Registry Editor, double-click **BAMTrackingEnabled**.</span></span>  
  
4.  <span data-ttu-id="f9b8b-110">在中**编辑 DWORD 值**对话框中**值数据**框中，键入**0**禁用 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-110">In the **Edit DWORD Value** dialog box, in the **Value data** box, type **0** to disable BAM tracking.</span></span>  
  
5.  <span data-ttu-id="f9b8b-111">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f9b8b-111">Click **OK**.</span></span>