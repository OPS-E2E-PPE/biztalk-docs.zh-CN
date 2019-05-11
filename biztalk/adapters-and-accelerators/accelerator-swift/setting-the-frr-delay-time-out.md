---
title: 设置 FRR 延迟超时 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring delay time-out
ms.assetid: 62209bf6-56c8-483a-96d5-328bffc8b680
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e141f1c2c3afff1049556c5bc041711695e9ca
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529984"
---
# <a name="setting-the-frr-delay-time-out"></a><span data-ttu-id="4a3c0-102">设置 FRR 延迟超时</span><span class="sxs-lookup"><span data-stu-id="4a3c0-102">Setting the FRR Delay Time-Out</span></span>
<span data-ttu-id="4a3c0-103">您必须配置 FRR 业务流程的某些时间段后，以便它不会等待 FNN 响应无限期。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-103">You must configure the FRR orchestration to time out after some duration, so it will not wait for the FNN response indefinitely.</span></span> <span data-ttu-id="4a3c0-104">如果在超时持续时间到期，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将超时消息发布到自定义超时处理程序。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-104">If the time-out duration expires, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] publishes the timed-out messages to a custom time-out handler.</span></span>  
  
### <a name="to-set-the-frr-delay-time-out"></a><span data-ttu-id="4a3c0-105">若要设置 FRR 延迟超时</span><span class="sxs-lookup"><span data-stu-id="4a3c0-105">To set the FRR delay time-out</span></span>  
  
1.  <span data-ttu-id="4a3c0-106">单击**启动**，单击**运行**，类型**regedit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4a3c0-107">在注册表编辑器的左窗格中，转到我的计算机/HKEY_LOCAL_MACHINE/软件/Microsoft/BizTalk Accelerator for SWIFT/FRR。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4a3c0-108">将角色将添加在角色节点中定义的工作流中的位置。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-108">The role will be added in the position in the workflow that is defined in the Roles node.</span></span> <span data-ttu-id="4a3c0-109">若要更改该位置，您需要执行步骤 8 以更改顺序角色节点中的角色。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-109">To change that position, you need to perform step 8 to change the order of the roles in the Roles node.</span></span>  
  
3.  <span data-ttu-id="4a3c0-110">在注册表编辑器的右窗格中，双击**DelayTimeout**。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-110">In the right pane of the Registry Editor, double-click **DelayTimeout**.</span></span>  
  
4.  <span data-ttu-id="4a3c0-111">在中**编辑 DWORD 值**对话框中**数值数据**框中，键入超时持续时间以十六进制格式。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-111">In the **Edit DWORD Value** dialog box, in the **Value data** box, type the time-out duration in hexadecimal format.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a3c0-112">默认值为**FRR DelayTimeout**属性为 600 秒 （258 十六进制格式）。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-112">The default value for the **FRR DelayTimeout** property is 600 seconds (258 Hexadecimal).</span></span>  
  
5.  <span data-ttu-id="4a3c0-113">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4a3c0-113">Click **OK**.</span></span>