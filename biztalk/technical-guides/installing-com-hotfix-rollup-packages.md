---
title: 安装 COM + 修补程序汇总包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 587ae3da-db65-4da8-9d3b-89effb91b197
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110dced7d3931e1987ccf966efffb700e1c5555b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020515"
---
# <a name="installing-com-hotfix-rollup-packages"></a><span data-ttu-id="d2881-102">安装 COM + 修补程序汇总包</span><span class="sxs-lookup"><span data-stu-id="d2881-102">Installing COM+ Hotfix Rollup Packages</span></span>
> [!NOTE]  
>  <span data-ttu-id="d2881-103">本主题是仅适用于 Windows Server 2003。</span><span class="sxs-lookup"><span data-stu-id="d2881-103">This topic is applicable only for Windows Server 2003.</span></span>  
  
 <span data-ttu-id="d2881-104">应安装的最后一个版本的 Windows Server 2003 COM + 修补程序汇总包和最新版本的分布式事务处理协调器 (DTC) 汇总包。</span><span class="sxs-lookup"><span data-stu-id="d2881-104">You should install the last version of the Windows Server 2003 COM+ hotfix rollup package and latest version of the Distributed Transaction Coordinator (DTC) rollup package.</span></span> <span data-ttu-id="d2881-105">这是因为包中包含许多性能和稳定性修复。</span><span class="sxs-lookup"><span data-stu-id="d2881-105">This is because the packages include many performance and stability fixes.</span></span>  
  
 <span data-ttu-id="d2881-106">你应该运行的所有计算机上安装这些汇总[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和运行 SQL Server 上的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="d2881-106">You should install these rollups on all computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and on all computers running SQL Server.</span></span> <span data-ttu-id="d2881-107">汇总会对您的 BizTalk 解决方案来执行在高吞吐量方案中尤其重要。</span><span class="sxs-lookup"><span data-stu-id="d2881-107">The rollups are especially important for your BizTalk solution to perform well in high-throughput scenarios.</span></span>  
  
 <span data-ttu-id="d2881-108">已修复的 DTC 问题如下所示：</span><span class="sxs-lookup"><span data-stu-id="d2881-108">The DTC issues that have been fixed are as follows:</span></span>  
  
- <span data-ttu-id="d2881-109">意外的 DTC 关闭</span><span class="sxs-lookup"><span data-stu-id="d2881-109">Unexpected DTC shutdown</span></span>  
  
- <span data-ttu-id="d2881-110">内存碎片问题</span><span class="sxs-lookup"><span data-stu-id="d2881-110">Memory fragmentation issues</span></span>  
  
- <span data-ttu-id="d2881-111">DTC 可能会停止响应负载</span><span class="sxs-lookup"><span data-stu-id="d2881-111">DTC may stop responding under load</span></span>  
  
- <span data-ttu-id="d2881-112">DTC 可能会泄漏内存或停止响应时与一起使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2881-112">DTC may leak memory or stop responding when used with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="d2881-113">改进了在负载下的 DTC 性能</span><span class="sxs-lookup"><span data-stu-id="d2881-113">Performance of DTC under load has been improved</span></span>  
  
## <a name="installing-the-com-rollup-package"></a><span data-ttu-id="d2881-114">安装 COM + 汇总包</span><span class="sxs-lookup"><span data-stu-id="d2881-114">Installing the COM+ Rollup Package</span></span>  
 <span data-ttu-id="d2881-115">COM + 无法再将发布汇总包。</span><span class="sxs-lookup"><span data-stu-id="d2881-115">COM+ is no longer releasing rollup packages.</span></span> <span data-ttu-id="d2881-116">请按照此信息来安装的最后一个的 COM + 包：</span><span class="sxs-lookup"><span data-stu-id="d2881-116">Follow this information to install the last COM+ package:</span></span>  
  
-   <span data-ttu-id="d2881-117">COM + 汇总的最终版本是"Windows Server 2003 Service Pack 2 COM + 1.5年修补程序汇总包 12年"。</span><span class="sxs-lookup"><span data-stu-id="d2881-117">The final version of the COM+ rollup is the “Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12”.</span></span> <span data-ttu-id="d2881-118">在任何版本的 Windows Server 2003，甚至是不带 service pack 的安装将安装此修补程序。</span><span class="sxs-lookup"><span data-stu-id="d2881-118">This hotfix will install on any version of Windows Server 2003, even those without a service pack installed.</span></span> <span data-ttu-id="d2881-119">有关此修补程序的详细信息可在 Microsoft 知识库文章 934016， ["可用性的 Windows Server 2003 Service Pack 2 COM + 1.5年修补程序汇总包 12年"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756)。</span><span class="sxs-lookup"><span data-stu-id="d2881-119">More information about this hotfix can be found in Microsoft Knowledge Base article 934016, ["Availability of Windows Server 2003 Post-Service Pack 2 COM+ 1.5 Hotfix Rollup Package 12"](http://go.microsoft.com/fwlink/?LinkId=158756) (http://go.microsoft.com/fwlink/?LinkId=158756).</span></span>  
  
## <a name="installing-the-dtc-rollup-package"></a><span data-ttu-id="d2881-120">安装 DTC 汇总包</span><span class="sxs-lookup"><span data-stu-id="d2881-120">Installing the DTC Rollup Package</span></span>  
 <span data-ttu-id="d2881-121">DTC 将同时发布独立于 COM + 汇总包。</span><span class="sxs-lookup"><span data-stu-id="d2881-121">DTC will be releasing rollup packages independent of COM+.</span></span> <span data-ttu-id="d2881-122">请按照此信息来安装最新的 DTC 包：</span><span class="sxs-lookup"><span data-stu-id="d2881-122">Follow this information to install the latest DTC package:</span></span>  
  
-   <span data-ttu-id="d2881-123">在撰写本文时，最新的 DTC 修补程序汇总是"包 16"。</span><span class="sxs-lookup"><span data-stu-id="d2881-123">As of this writing, the latest DTC hotfix rollup is “Package 16”.</span></span> <span data-ttu-id="d2881-124">在 Microsoft 知识库文章 958013，可以找到有关此修补程序详细信息["在 Windows Server 2003 MS DTC 修补程序汇总包 16 中修复的 MS DTC 问题的列表"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919)。</span><span class="sxs-lookup"><span data-stu-id="d2881-124">More information about this hotfix can be found in Microsoft Knowledge Base article 958013, ["List of the MS DTC issues that are fixed in Windows Server 2003 MS DTC Hotfix Rollup Package 16"](http://support.microsoft.com/kb/979919) (http://support.microsoft.com/kb/979919).</span></span>  
  
     <span data-ttu-id="d2881-125">可以通过搜索找到最新的 DTC 修补程序汇总包有关的 KB 文章[ http://support.microsoft.com ](http://support.microsoft.com/)短语 （包括引号）：</span><span class="sxs-lookup"><span data-stu-id="d2881-125">The KB article about the latest DTC hotfix rollup package can be found by searching [http://support.microsoft.com](http://support.microsoft.com/) for the phrase (including the quotes):</span></span>  
  
    ```  
    "MS DTC Hotfix Rollup Package"  
    ```  
  
     <span data-ttu-id="d2881-126">下面的查询执行此搜索。</span><span class="sxs-lookup"><span data-stu-id="d2881-126">The following query does this search for you.</span></span> <span data-ttu-id="d2881-127">选择最新版本：</span><span class="sxs-lookup"><span data-stu-id="d2881-127">Choose the latest one:</span></span>  
  
     [<span data-ttu-id="d2881-128">http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"</span><span class="sxs-lookup"><span data-stu-id="d2881-128">http://support.microsoft.com/search/default.aspx?query="MS+DTC+Hotfix+Rollup+Package"</span></span>](http://support.microsoft.com/search/default.aspx?query=%22MS+DTC+Hotfix+Rollup+Package%22)