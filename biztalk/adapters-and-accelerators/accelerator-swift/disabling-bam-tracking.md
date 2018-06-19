---
title: 禁用 BAM 跟踪 |Microsoft 文档
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
ms.openlocfilehash: e4e734bd31147ecacc8bbbe98d98297edfb4f0de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209045"
---
# <a name="disabling-bam-tracking"></a><span data-ttu-id="d16e7-102">禁用 BAM 跟踪</span><span class="sxs-lookup"><span data-stu-id="d16e7-102">Disabling BAM Tracking</span></span>
<span data-ttu-id="d16e7-103">默认情况下，为 FIN 响应对帐启用了 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="d16e7-103">By default, BAM tracking is enabled for FIN Response Reconciliation.</span></span> <span data-ttu-id="d16e7-104">可以禁用它，如下所示。</span><span class="sxs-lookup"><span data-stu-id="d16e7-104">You can disable it as follows.</span></span>  
  
### <a name="to-disable-bam-tracking-for-frr"></a><span data-ttu-id="d16e7-105">若要禁用跟踪 FRR BAM</span><span class="sxs-lookup"><span data-stu-id="d16e7-105">To disable BAM tracking for FRR</span></span>  
  
1.  <span data-ttu-id="d16e7-106">单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d16e7-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d16e7-107">在注册表编辑器的左窗格中，移动到我的计算机/HKEY_LOCAL_MACHINE/软件/Microsoft/BizTalk Accelerator for SWIFT/FRR。</span><span class="sxs-lookup"><span data-stu-id="d16e7-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d16e7-108">必须在运行 FIN 响应对帐每台计算机上修改此注册表项。</span><span class="sxs-lookup"><span data-stu-id="d16e7-108">This registry entry must be modified on each computer that FIN Response Reconciliation is running on.</span></span>  
  
3.  <span data-ttu-id="d16e7-109">在注册表编辑器的右窗格中，双击**BAMTrackingEnabled**。</span><span class="sxs-lookup"><span data-stu-id="d16e7-109">In the right pane of the Registry Editor, double-click **BAMTrackingEnabled**.</span></span>  
  
4.  <span data-ttu-id="d16e7-110">在**编辑 DWORD 值**对话框中，在**值数据**框中，键入**0**禁用 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="d16e7-110">In the **Edit DWORD Value** dialog box, in the **Value data** box, type **0** to disable BAM tracking.</span></span>  
  
5.  <span data-ttu-id="d16e7-111">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d16e7-111">Click **OK**.</span></span>