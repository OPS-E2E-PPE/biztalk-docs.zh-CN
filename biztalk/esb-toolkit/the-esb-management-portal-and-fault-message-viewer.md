---
title: "ESB 管理门户和错误消息查看器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4a1636c-2e45-4ee5-92c2-81c976582da3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9a6e7272e7b707b6ba7650cfb93506c3a54a00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a><span data-ttu-id="2249b-102">ESB 管理门户和错误消息查看器</span><span class="sxs-lookup"><span data-stu-id="2249b-102">The ESB Management Portal and Fault Message Viewer</span></span>
<span data-ttu-id="2249b-103">一个主要组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是基于 Web 的门户，提供了各种各样的异常管理和警报通知功能; 此外，它作为有用的配置管理和通用、 描述、 发现和集成 （UDDI) 注册接口。</span><span class="sxs-lookup"><span data-stu-id="2249b-103">A major component of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is a Web-based portal that provides a wide range of exception management and alert notification features; in addition, it acts as a useful configuration management and Universal Description, Discovery, and Integration (UDDI) registration interface.</span></span> <span data-ttu-id="2249b-104">图 1 显示一个门户，它概述了运行状况当前正在运行的应用程序的主页。</span><span class="sxs-lookup"><span data-stu-id="2249b-104">Figure 1 shows the home page of the portal, which provides an overview of the health of the currently running applications.</span></span>  
  
 <span data-ttu-id="2249b-105">![门户主页上](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")</span><span class="sxs-lookup"><span data-stu-id="2249b-105">![Portal Home Page](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")</span></span>  
  
 <span data-ttu-id="2249b-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="2249b-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="2249b-107">**ESB 管理门户的主页页面**</span><span class="sxs-lookup"><span data-stu-id="2249b-107">**The home page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="2249b-108">用户可以选择在 ESB 管理门户中显示的错误消息以查看错误的环境和静态属性和错误消息中包含的原始消息的列表，如图 2 中所示。</span><span class="sxs-lookup"><span data-stu-id="2249b-108">Users can select a fault message displayed in the ESB Management Portal to view the ambient and static properties of the fault and a list of the original messages contained in the fault message, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="2249b-109">![Faul tViewer 页](../esb-toolkit/media/ch4-faultviewerpage.gif "第四章第 4 FaultViewerPage")</span><span class="sxs-lookup"><span data-stu-id="2249b-109">![Faul tViewer Page](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4-FaultViewerPage")</span></span>  
  
 <span data-ttu-id="2249b-110">**图 2**</span><span class="sxs-lookup"><span data-stu-id="2249b-110">**Figure 2**</span></span>  
  
 <span data-ttu-id="2249b-111">**ESB 管理门户的 ESB 错误查看器页上**</span><span class="sxs-lookup"><span data-stu-id="2249b-111">**The ESB Fault Viewer page of the ESB Management Portal**</span></span>  
  
 <span data-ttu-id="2249b-112">ESB 管理门户中显示的 ESB 错误消息可能时提交以供处理的原始消息的值中的错误的结果。</span><span class="sxs-lookup"><span data-stu-id="2249b-112">ESB Fault messages displayed in the ESB Management Portal may be the result of an error in the values of the original message when submitted for processing.</span></span> <span data-ttu-id="2249b-113">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持"修复并重新提交"功能，这将允许管理员或用户编辑失败的消息以及将其提交至入口进行处理。</span><span class="sxs-lookup"><span data-stu-id="2249b-113">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports "repair and resubmit" functionality, which allows administrators or users to edit failed messages and to submit them to an on-ramp for processing.</span></span>  
  
 <span data-ttu-id="2249b-114">选择其中一个包含的消息打开消息视图页在消息详细信息视图中，如图 3 中所示。</span><span class="sxs-lookup"><span data-stu-id="2249b-114">Selecting one of the contained messages opens the Message View page in Message Details view, as shown in Figure 3.</span></span> <span data-ttu-id="2249b-115">在此视图中，用户可以看到的消息内容，下载消息，或单击**编辑**切换到编辑视图，它们可以在位置修复并重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="2249b-115">In this view, users can see the message content, download the message, or click **Edit** to switch to Edit view, where they can repair and resubmit the message.</span></span>  
  
 <span data-ttu-id="2249b-116">![消息查看器页面](../esb-toolkit/media/ch4-messageviewerpage.gif "第四章第 4 MessageViewerPage")</span><span class="sxs-lookup"><span data-stu-id="2249b-116">![Message Viewer Page](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4-MessageViewerPage")</span></span>  
  
 <span data-ttu-id="2249b-117">**图 3**</span><span class="sxs-lookup"><span data-stu-id="2249b-117">**Figure 3**</span></span>  
  
 <span data-ttu-id="2249b-118">**显示的错误详细信息视图的 ESB 消息查看器**</span><span class="sxs-lookup"><span data-stu-id="2249b-118">**The ESB Message Viewer showing the Fault Details view**</span></span>  
  
 <span data-ttu-id="2249b-119">有关完整说明和 ESB 管理门户中，包括错误查看器、 消息重新提交过程中和有关列表，采用的技术的使用情况选项排序和分析错误，请参阅[借助 BizTalk ESB 管理工具包](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)。</span><span class="sxs-lookup"><span data-stu-id="2249b-119">For a complete description and usage options of the ESB Management Portal, including the Fault Viewer, the message resubmission process, and the techniques used for listing, sorting, and analyzing faults, see [Administration with the BizTalk ESB Toolkit](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md).</span></span>