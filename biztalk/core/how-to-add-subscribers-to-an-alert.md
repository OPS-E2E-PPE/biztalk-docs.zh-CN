---
title: 如何向警报添加订户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- subscriptions
- managing [BAM], adding alert subscribers
ms.assetid: c76a117d-4516-4f48-995c-7e018dbba755
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 034415c8252a8e8adde51136b11185803d39af40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387224"
---
# <a name="how-to-add-subscribers-to-an-alert"></a><span data-ttu-id="21c12-102">如何向警报添加订户</span><span class="sxs-lookup"><span data-stu-id="21c12-102">How to Add Subscribers to an Alert</span></span>
<span data-ttu-id="21c12-103">管理员使用**添加订阅**命令将订阅服务器添加到指定的警报。</span><span class="sxs-lookup"><span data-stu-id="21c12-103">Administrators use the **add-subscription** command to add a subscriber to a specified alert.</span></span>  
  
### <a name="to-add-subscribers-to-an-alert"></a><span data-ttu-id="21c12-104">向警报添加订户</span><span class="sxs-lookup"><span data-stu-id="21c12-104">To add subscribers to an alert</span></span>  
  
1. <span data-ttu-id="21c12-105">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="21c12-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="21c12-106">通过键入导航到跟踪文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪在命令提示符处。</span><span class="sxs-lookup"><span data-stu-id="21c12-106">Navigate to the tracking folder by typing [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking at the command prompt.</span></span> <span data-ttu-id="21c12-107">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="21c12-107">Press **ENTER**.</span></span>  
  
3. <span data-ttu-id="21c12-108">键入 `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`。</span><span class="sxs-lookup"><span data-stu-id="21c12-108">Type `bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21c12-109">*类型*指定 BAM 用来传送警报的传递方法。</span><span class="sxs-lookup"><span data-stu-id="21c12-109">*Type* specifies the delivery method which BAM uses to deliver the alert.</span></span> <span data-ttu-id="21c12-110">如果指定的电子邮件传递类型必须提供向其传递该警报的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="21c12-110">If you specify a delivery type of e-mail you must supply an e-mail address to which the alert is delivered.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21c12-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="21c12-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="21c12-112">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="21c12-112">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c12-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="21c12-113">See Also</span></span>  
 <span data-ttu-id="21c12-114">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="21c12-114">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="21c12-115">[BAM 管理实用程序](../core/bam-management-utility.md) </span><span class="sxs-lookup"><span data-stu-id="21c12-115">[BAM Management Utility](../core/bam-management-utility.md) </span></span>  
 [<span data-ttu-id="21c12-116">如何从警报删除订户</span><span class="sxs-lookup"><span data-stu-id="21c12-116">How to Remove Subscribers from an Alert</span></span>](../core/how-to-remove-subscribers-from-an-alert.md)