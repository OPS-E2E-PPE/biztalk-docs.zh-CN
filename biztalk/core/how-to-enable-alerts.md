---
title: 如何启用警报 |Microsoft 文档
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
ms.openlocfilehash: 9986bea177471a236cab888f20d915292d540e5b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968819"
---
# <a name="how-to-enable-alerts"></a><span data-ttu-id="de376-102">如何启用警报</span><span class="sxs-lookup"><span data-stu-id="de376-102">How to Enable Alerts</span></span>
<span data-ttu-id="de376-103">管理员使用**启用警报**命令启用所有指定的视图上的警报。</span><span class="sxs-lookup"><span data-stu-id="de376-103">Administrators use the **enable-alerts** command to enable all of the alerts on the specified view.</span></span>  
  
### <a name="to-enable-an-alert"></a><span data-ttu-id="de376-104">若要启用的警报</span><span class="sxs-lookup"><span data-stu-id="de376-104">To enable an alert</span></span>  
  
1.  <span data-ttu-id="de376-105">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="de376-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="de376-106">通过在命令提示符处键入 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking，导航到跟踪文件夹。</span><span class="sxs-lookup"><span data-stu-id="de376-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="de376-107">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="de376-107">Press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="de376-108">类型**bm 启用警报的视图：\<视图名称\>**。</span><span class="sxs-lookup"><span data-stu-id="de376-108">Type **bm enable-alerts -View:\<view name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de376-109">如果您已经将 BAM 配置作为 XML 导出，则不要修改与警报相关的 XML。</span><span class="sxs-lookup"><span data-stu-id="de376-109">If you have exported a BAM configuration as XML, do not modify the XML related to alerts.</span></span> <span data-ttu-id="de376-110">如果您更改与警报相关的 XML 并部署这些更改，则 bm.exe 将检测到该更改并启用 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="de376-110">If you change XML related to alerts and deploy the changes, bm.exe will detect the change and enable BAM alerts.</span></span>  
  
4.  <span data-ttu-id="de376-111">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="de376-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de376-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de376-112">See Also</span></span>  
 <span data-ttu-id="de376-113">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="de376-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="de376-114">[BAM 管理实用工具](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="de376-114">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="de376-115">在此处输入链接说明</span><span class="sxs-lookup"><span data-stu-id="de376-115">enter link description here</span></span>](../core/how-to-disable-alerts.md)