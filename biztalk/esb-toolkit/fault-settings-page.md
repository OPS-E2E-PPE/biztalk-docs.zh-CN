---
title: "错误设置页 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67f10b8b-9a32-40ca-9ce4-0b69e159c36c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ce03e5284122e8c1de9bd4e5c2d69c392174e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fault-settings-page"></a><span data-ttu-id="338a3-102">“错误设置”页</span><span class="sxs-lookup"><span data-stu-id="338a3-102">Fault Settings Page</span></span>
<span data-ttu-id="338a3-103">图 1 显示的错误设置页。</span><span class="sxs-lookup"><span data-stu-id="338a3-103">Figure 1 shows the Fault Settings page.</span></span> <span data-ttu-id="338a3-104">此页显示了一系列的可修改的管理设置。</span><span class="sxs-lookup"><span data-stu-id="338a3-104">This page displays a range of administrative settings that you can modify.</span></span>  
  
 <span data-ttu-id="338a3-105">![错误设置页](../esb-toolkit/media/ch8-faultsettingspage.gif "Ch8 FaultSettingsPage")</span><span class="sxs-lookup"><span data-stu-id="338a3-105">![Fault Settings Page](../esb-toolkit/media/ch8-faultsettingspage.gif "Ch8-FaultSettingsPage")</span></span>  
  
 <span data-ttu-id="338a3-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="338a3-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="338a3-107">**ESB 管理门户错误设置页**</span><span class="sxs-lookup"><span data-stu-id="338a3-107">**The ESB Management Portal Fault Settings page**</span></span>  
  
 <span data-ttu-id="338a3-108">以下列表说明如何使用 ESB 管理门户错误设置页的功能：</span><span class="sxs-lookup"><span data-stu-id="338a3-108">The following list explains how you can use the features of the ESB Management Portal Fault Settings page:</span></span>  
  
-   <span data-ttu-id="338a3-109">若要更改的审核选项，选择你要审核每个事件对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="338a3-109">To change the audit options, select the check boxes for each event you want to audit.</span></span> <span data-ttu-id="338a3-110">当重新提交错误时，可用的事件将非常保存修改后的设置，编辑和失败后成功重新提交错误。</span><span class="sxs-lookup"><span data-stu-id="338a3-110">The available events are the saving of modified settings, successful resubmission of a fault after editing, and failure when resubmitting a fault.</span></span>  
  
-   <span data-ttu-id="338a3-111">门户维护 Portal Alert 服务生成的警报的队列。</span><span class="sxs-lookup"><span data-stu-id="338a3-111">The portal maintains a queue of the alerts generated by the Portal Alert service.</span></span> <span data-ttu-id="338a3-112">你可以修改此服务中设置**警报队列选项**页的部分。</span><span class="sxs-lookup"><span data-stu-id="338a3-112">You can modify the settings for this service in the **Alert Queue Options** section of the page.</span></span> <span data-ttu-id="338a3-113">可以启用或禁用服务，指定与 Microsoft Active Directory 目录服务，其交互和控制的队列批大小和轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="338a3-113">You can enable or disable the service, specify its interaction with Microsoft Active Directory directory service, and control the queue batch size and polling interval.</span></span>  
  
-   <span data-ttu-id="338a3-114">若要更改的警报的电子邮件服务的设置，请使用中的控件**警报的电子邮件选项**页的部分。</span><span class="sxs-lookup"><span data-stu-id="338a3-114">To change the settings for the Alert Email service, use the controls in the **Alert Email Options** section of the page.</span></span> <span data-ttu-id="338a3-115">你可以启用或禁用该服务;指定电子邮件服务器和的"发件人"地址;更改轮询间隔和批处理大小;并指定服务使用的 XSLT 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="338a3-115">You can enable or disable the service; specify the e-mail server and the "from" address; change the polling interval and batch size; and specify the path to XSLT files that the service uses.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="338a3-116">安装和配置 ESB 门户和 Portal Alert 服务时，你必须在此页中输入值。</span><span class="sxs-lookup"><span data-stu-id="338a3-116">You must enter the values in this page when you install and configure the ESB Portal and the Portal Alert service.</span></span> <span data-ttu-id="338a3-117">有关详细信息，请参阅[安装 ESB 管理门户](http://go.microsoft.com/fwlink/?LinkId=188554)。</span><span class="sxs-lookup"><span data-stu-id="338a3-117">For more information, see [Installing the ESB Management Portal](http://go.microsoft.com/fwlink/?LinkId=188554).</span></span>