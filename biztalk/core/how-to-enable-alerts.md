---
title: 如何启用警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9fee863613feea040e05856d8246f94b4a3f835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969150"
---
# <a name="how-to-enable-alerts"></a><span data-ttu-id="b0289-102">如何启用警报</span><span class="sxs-lookup"><span data-stu-id="b0289-102">How to Enable Alerts</span></span>
<span data-ttu-id="b0289-103">管理员使用**启用警报**命令以启用所有指定的视图上的警报。</span><span class="sxs-lookup"><span data-stu-id="b0289-103">Administrators use the **enable-alerts** command to enable all of the alerts on the specified view.</span></span>  
  
### <a name="to-enable-an-alert"></a><span data-ttu-id="b0289-104">若要启用的警报</span><span class="sxs-lookup"><span data-stu-id="b0289-104">To enable an alert</span></span>  
  
1. <span data-ttu-id="b0289-105">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b0289-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="b0289-106">通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。</span><span class="sxs-lookup"><span data-stu-id="b0289-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="b0289-107">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="b0289-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="b0289-108">类型**bm 启用警报的视图：\<视图名称\>**。</span><span class="sxs-lookup"><span data-stu-id="b0289-108">Type **bm enable-alerts -View:\<view name\>**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b0289-109">如果您已经将 BAM 配置作为 XML 导出，则不要修改与警报相关的 XML。</span><span class="sxs-lookup"><span data-stu-id="b0289-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="b0289-110">如果您更改与警报相关的 XML 并部署这些更改，则 bm.exe 将检测到该更改并启用 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="b0289-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4. <span data-ttu-id="b0289-111">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="b0289-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0289-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0289-112">See Also</span></span>  
 <span data-ttu-id="b0289-113">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="b0289-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="b0289-114">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b0289-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="b0289-115">在此处输入链接说明</span><span class="sxs-lookup"><span data-stu-id="b0289-115">enter link description here</span></span>](../core/how-to-disable-alerts.md)