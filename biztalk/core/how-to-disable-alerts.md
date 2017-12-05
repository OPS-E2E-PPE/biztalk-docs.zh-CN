---
title: "如何禁用警报 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4279030b9c3bcc7913bf64cc870b0d82d618dff8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-disable-alerts"></a><span data-ttu-id="5e3da-102">如何禁用警报</span><span class="sxs-lookup"><span data-stu-id="5e3da-102">How to Disable Alerts</span></span>
<span data-ttu-id="5e3da-103">管理员使用**禁用警报**命令以禁用所有指定的视图上的警报。</span><span class="sxs-lookup"><span data-stu-id="5e3da-103">Administrators use the **disable-alerts** command to disable all of the alerts on the specified view.</span></span>  
  
### <a name="to-disable-an-alert"></a><span data-ttu-id="5e3da-104">若要禁用警报</span><span class="sxs-lookup"><span data-stu-id="5e3da-104">To disable an alert</span></span>  
  
1.  <span data-ttu-id="5e3da-105">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5e3da-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="5e3da-106">通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。</span><span class="sxs-lookup"><span data-stu-id="5e3da-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="5e3da-107">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="5e3da-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="5e3da-108">类型**bm 禁用警报的视图：\<视图名称\>**。</span><span class="sxs-lookup"><span data-stu-id="5e3da-108">Type **bm disable-alerts -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e3da-109">如果您已经将 BAM 配置作为 XML 导出，则不要修改与警报相关的 XML。</span><span class="sxs-lookup"><span data-stu-id="5e3da-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="5e3da-110">如果您更改与警报相关的 XML 并部署这些更改，则 bm.exe 将检测到该更改并启用 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="5e3da-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4.  <span data-ttu-id="5e3da-111">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="5e3da-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3da-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e3da-112">See Also</span></span>  
 <span data-ttu-id="5e3da-113">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="5e3da-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="5e3da-114">[BAM 管理实用工具](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="5e3da-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="5e3da-115">如何启用警报</span><span class="sxs-lookup"><span data-stu-id="5e3da-115">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md)