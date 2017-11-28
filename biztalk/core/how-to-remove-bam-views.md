---
title: "如何删除 BAM 视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d8930fb4e3f2014945b743b15da4dbdfff3451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-bam-views"></a><span data-ttu-id="34916-102">如何删除 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="34916-102">How to Remove BAM Views</span></span>
<span data-ttu-id="34916-103">管理员使用**删除视图**命令从 BAM 主导入数据库中删除视图。</span><span class="sxs-lookup"><span data-stu-id="34916-103">Administrators use the **remove-view** command to remove a view from the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34916-104">在删除视图时，还会自动删除为该视图定义的所有警报。</span><span class="sxs-lookup"><span data-stu-id="34916-104">When you remove a view, you also automatically remove any alerts defined for that view.</span></span>  
  
### <a name="to-remove-bam-views"></a><span data-ttu-id="34916-105">若要删除 BAM 视图</span><span class="sxs-lookup"><span data-stu-id="34916-105">To remove BAM views</span></span>  
  
1.  <span data-ttu-id="34916-106">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="34916-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="34916-107">导航到的跟踪文件夹中，通过键入**C:\Program Files\Microsoft BizTalk Server 2009\Tracking**在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="34916-107">Navigate to the tracking folder by typing **C:\Program Files\Microsoft BizTalk Server 2009\Tracking** at the command prompt.</span></span> <span data-ttu-id="34916-108">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="34916-108">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="34916-109">类型**bm 删除视图的名称：\<视图名称 >**。</span><span class="sxs-lookup"><span data-stu-id="34916-109">Type **bm remove-view -Name:\<view name>**.</span></span>  
  
4.  <span data-ttu-id="34916-110">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="34916-110">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34916-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34916-111">See Also</span></span>  
 <span data-ttu-id="34916-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="34916-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="34916-113">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="34916-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 <span data-ttu-id="34916-114">[BAM 管理实用工具](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="34916-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="34916-115">如何删除 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="34916-115">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)