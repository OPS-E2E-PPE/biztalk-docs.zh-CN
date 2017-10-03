---
title: "安装 COM + 修补程序汇总包 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40610c649e00993323adedf0ea29330dd289a0e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="installing-com-hotfix-rollup-packages"></a><span data-ttu-id="3eba7-102">安装 COM + 修补程序汇总包</span><span class="sxs-lookup"><span data-stu-id="3eba7-102">Installing COM+ Hotfix Rollup Packages</span></span>
> [!NOTE]  
>  <span data-ttu-id="3eba7-103">本主题是仅适用于 Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="3eba7-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="3eba7-104">你应安装了上一版本的 Windows Server 2003 COM + 修补程序汇总包和最新版本的分布式事务处理协调器 (DTC) 汇总包。</span><span class="sxs-lookup"><span data-stu-id="3eba7-104">You should install the last version of the Windows Server 2003 COM+ hotfix rollup package and latest version of the Distributed Transaction Coordinator (DTC) rollup package.</span></span> <span data-ttu-id="3eba7-105">这是因为包中包含许多性能和稳定性的修补程序。</span><span class="sxs-lookup"><span data-stu-id="3eba7-105">This is because the packages include many performance and stability fixes.</span></span>  
  
 <span data-ttu-id="3eba7-106">应运行的所有计算机上安装这些汇总[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和运行 SQL Server 上的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="3eba7-106">You should install these rollups on all computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and on all computers running SQL Server.</span></span> <span data-ttu-id="3eba7-107">汇总尤其是对于非常重要 BizTalk 解决方案以高吞吐量方案中良好地执行。</span><span class="sxs-lookup"><span data-stu-id="3eba7-107">The rollups are especially important for your BizTalk solution to perform well in high-throughput scenarios.</span></span>  
  
 <span data-ttu-id="3eba7-108">已修复的 DTC 问题如下所示：</span><span class="sxs-lookup"><span data-stu-id="3eba7-108">The DTC issues that have been fixed are as follows:</span></span>  
  
-   <span data-ttu-id="3eba7-109">意外的 DTC 关闭</span><span class="sxs-lookup"><span data-stu-id="3eba7-109">Unexpected DTC shutdown</span></span>  
  
-   <span data-ttu-id="3eba7-110">内存碎片问题</span><span class="sxs-lookup"><span data-stu-id="3eba7-110">Memory fragmentation issues</span></span>  
  
-   <span data-ttu-id="3eba7-111">DTC 可能会停止在负载下作出响应</span><span class="sxs-lookup"><span data-stu-id="3eba7-111">DTC may stop responding under load</span></span>  
  
-   <span data-ttu-id="3eba7-112">DTC 可能会泄漏内存或停止响应一起使用时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eba7-112">DTC may leak memory or stop responding when used with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="3eba7-113">DTC 负载的性能已改进</span><span class="sxs-lookup"><span data-stu-id="3eba7-113">Performance of DTC under load has been improved</span></span>  
  
## <a name="installing-the-com-rollup-package"></a><span data-ttu-id="3eba7-114">安装 COM + 汇总包</span><span class="sxs-lookup"><span data-stu-id="3eba7-114">Installing the COM+ Rollup Package</span></span>  
 <span data-ttu-id="3eba7-115">COM + 不再释放汇总包。</span><span class="sxs-lookup"><span data-stu-id="3eba7-115">COM+ is no longer releasing rollup packages.</span></span> <span data-ttu-id="3eba7-116">请按照此信息来安装的最后一个的 COM + 包：</span><span class="sxs-lookup"><span data-stu-id="3eba7-116">Follow this information to install the last COM+ package:</span></span>  
  
-   <span data-ttu-id="3eba7-117">COM + 汇总的最终版本是"Windows Server 2003 Post-service Pack 2 COM + 1.5年修补程序汇总包 12年"。</span><span class="sxs-lookup"><span data-stu-id="3eba7-117">The final version of the COM+ rollup is the “Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12”.</span></span> <span data-ttu-id="3eba7-118">此修补程序将安装在 Windows Server 2003，甚至那些不带 service pack 安装的任何版本上。</span><span class="sxs-lookup"><span data-stu-id="3eba7-118">This hotfix will install on any version of Windows Server 2003, even those without a service pack installed.</span></span> <span data-ttu-id="3eba7-119">有关此修补程序的详细信息可在 Microsoft 知识库文章 934016， ["可用性的 Windows Server 2003 Post-service Pack 2 COM + 1.5年修补程序汇总包 12年"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756)。</span><span class="sxs-lookup"><span data-stu-id="3eba7-119">More information about this hotfix can be found in Microsoft Knowledge Base article 934016, ["Availability of Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).</span></span>  
  
## <a name="installing-the-dtc-rollup-package"></a><span data-ttu-id="3eba7-120">安装 DTC 汇总包</span><span class="sxs-lookup"><span data-stu-id="3eba7-120">Installing the DTC Rollup Package</span></span>  
 <span data-ttu-id="3eba7-121">DTC 即将发布的 COM + 独立汇总包。</span><span class="sxs-lookup"><span data-stu-id="3eba7-121">DTC will be releasing rollup packages independent of COM+.</span></span> <span data-ttu-id="3eba7-122">请遵循此信息来安装最新的 DTC 包：</span><span class="sxs-lookup"><span data-stu-id="3eba7-122">Follow this information to install the latest DTC package:</span></span>  
  
-   <span data-ttu-id="3eba7-123">截至撰写本文时，最新的 DTC 修补程序汇总为"包 16"。</span><span class="sxs-lookup"><span data-stu-id="3eba7-123">As of this writing, the latest DTC hotfix rollup is “Package 16”.</span></span> <span data-ttu-id="3eba7-124">有关此修补程序的详细信息可在 Microsoft 知识库文章 958013， ["List of Windows Server 2003 MS DTC 修补程序汇总包 16 中修复的 MS DTC 问题"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span><span class="sxs-lookup"><span data-stu-id="3eba7-124">More information about this hotfix can be found in Microsoft Knowledge Base article 958013, ["List of the MS DTC issues that are fixed in Windows Server 2003 MS DTC Hotfix Rollup Package 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span></span>  
  
     <span data-ttu-id="3eba7-125">可以通过搜索找到有关最新的 DTC 修补程序汇总包的 KB 文章[http://support.microsoft.com](http://support.microsoft.com/)短语 （包括引号）：</span><span class="sxs-lookup"><span data-stu-id="3eba7-125">The KB article about the latest DTC hotfix rollup package can be found by searching [http://support.microsoft.com](http://support.microsoft.com/) for the phrase (including the quotes):</span></span>  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     <span data-ttu-id="3eba7-126">下面的查询执行此搜索。</span><span class="sxs-lookup"><span data-stu-id="3eba7-126">The following query does this search for you.</span></span> <span data-ttu-id="3eba7-127">选择的最新项目：</span><span class="sxs-lookup"><span data-stu-id="3eba7-127">Choose the latest one:</span></span>  
  
     [<span data-ttu-id="3eba7-128">http://support.microsoft.com/search/default.aspx?query="MS + DTC + 修补程序 + 汇总 + 包"</span><span class="sxs-lookup"><span data-stu-id="3eba7-128">http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"</span></span>](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)