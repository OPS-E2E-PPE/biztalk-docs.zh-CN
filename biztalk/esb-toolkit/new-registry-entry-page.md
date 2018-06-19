---
title: 新的注册表条目页 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 204c547c-ed0e-4a1f-a0b2-ce5da00d9c42
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56fa56bff9d1418cc54430a6ab61140821a4ccc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294389"
---
# <a name="new-registry-entry-page"></a><span data-ttu-id="e689b-102">“新建注册表项”页</span><span class="sxs-lookup"><span data-stu-id="e689b-102">New Registry Entry Page</span></span>
<span data-ttu-id="e689b-103">图 1 显示的 ESB 管理门户新注册表条目页你可以在其中查看在指定的 Microsoft BizTalk Server ESB 应用程序中存在现有终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="e689b-103">Figure 1 shows the ESB Management Portal New Registry Entry page where you can view a list of the existing endpoints in a specified Microsoft BizTalk Server ESB application.</span></span>  
  
 <span data-ttu-id="e689b-104">![新的注册表条目页](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8 NewRegistryEntryPage")</span><span class="sxs-lookup"><span data-stu-id="e689b-104">![New Registry Entry Page](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8-NewRegistryEntryPage")</span></span>  
  
 <span data-ttu-id="e689b-105">**图 1**</span><span class="sxs-lookup"><span data-stu-id="e689b-105">**Figure 1**</span></span>  
  
 <span data-ttu-id="e689b-106">**ESB 管理门户新注册表项页**</span><span class="sxs-lookup"><span data-stu-id="e689b-106">**The ESB Management Portal New Registry Entry page**</span></span>  
  
 <span data-ttu-id="e689b-107">以下列表说明如何使用 ESB 管理门户新注册表项页的功能：</span><span class="sxs-lookup"><span data-stu-id="e689b-107">The following list explains how you can use the features of the ESB Management Portal New Registry Entry page:</span></span>  
  
-   <span data-ttu-id="e689b-108">使用页面顶部附近的三个下拉列表来指定类型、 状态和 BizTalk 应用程序包含你想要查看的终结点：</span><span class="sxs-lookup"><span data-stu-id="e689b-108">Use the three drop-down lists near the top of the page to specify the type, status, and BizTalk application that contains the endpoints you want to view:</span></span>  
  
    -   <span data-ttu-id="e689b-109">在第一个 （终结点类型） 下拉列表中，你可以选择**接收位置、 发送端口**或**所有终结点**。</span><span class="sxs-lookup"><span data-stu-id="e689b-109">In the first (endpoint type) drop-down list, you can select **Receive Locations, Send Ports,** or **All Endpoints**.</span></span>  
  
    -   <span data-ttu-id="e689b-110">在第二个 （状态） 下拉列表中，你可以选择**已注册、 NotRegistered，挂起，** 或**所有**。</span><span class="sxs-lookup"><span data-stu-id="e689b-110">In the second (status) drop-down list, you can select **Registered, NotRegistered, Pending,** or **All**.</span></span>  
  
    -   <span data-ttu-id="e689b-111">在第三个 （BizTalk 应用程序） 下拉列表中，你可以选择当前已安装 BizTalk 应用程序之一。</span><span class="sxs-lookup"><span data-stu-id="e689b-111">In the third (BizTalk application) drop-down list, you can select one of the currently installed BizTalk applications.</span></span>  
  
-   <span data-ttu-id="e689b-112">在指定的应用程序和终结点的条件之后, 单击 BizTalk 应用程序下拉列表，以显示匹配的终结点的列表旁边的箭头图标。</span><span class="sxs-lookup"><span data-stu-id="e689b-112">After specifying the application and endpoint criteria, click the arrow icon next to the BizTalk application drop-down list to display a list of matching endpoints.</span></span>  
  
-   <span data-ttu-id="e689b-113">终结点的列表包含匹配的终结点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e689b-113">The list of endpoints contains details of matching endpoints.</span></span> <span data-ttu-id="e689b-114">为每个不是动态的终结点，该列表包含可用于查看和编辑发布此终结点的待处理请求的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="e689b-114">For each one that is not a dynamic endpoint, the list contains a link that allows you to view and edit the details of a pending request to publish this endpoint.</span></span>  
  
-   <span data-ttu-id="e689b-115">单击**查看详细信息**列表后，若要打开的任何行中的链接[注册表的详细信息页](../esb-toolkit/registry-details-page.md)其中你可以修改请求，并将发布终结点。</span><span class="sxs-lookup"><span data-stu-id="e689b-115">Click the **View Detail** link in any row of the list to open the [Registry Details Page](../esb-toolkit/registry-details-page.md) where you can modify the request and publish the endpoint.</span></span>