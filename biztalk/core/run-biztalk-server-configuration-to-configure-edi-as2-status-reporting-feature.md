---
title: "若要启用状态报告、 运行和 #39;BizTalk Server 配置 &#39;和配置 EDI AS2 状态报告功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf125919-80ab-4cb8-b1f5-0f2616cc6f5c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 334e77ed58d460aea3ca37f73c1165d62da0f10b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="to-enable-status-reporting-run-39biztalk-server-configuration39-and-configure-edi-as2-status-reporting-feature"></a><span data-ttu-id="ff91f-102">若要启用状态报告、 运行和 #39;BizTalk Server 配置 &#39;和配置 EDI AS2 状态报告功能</span><span class="sxs-lookup"><span data-stu-id="ff91f-102">To enable status reporting, run &#39;BizTalk Server Configuration&#39; and configure EDI-AS2 status reporting feature</span></span>
## <a name="details"></a><span data-ttu-id="ff91f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ff91f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff91f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ff91f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ff91f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ff91f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ff91f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ff91f-106">Event ID</span></span>|-|  
|<span data-ttu-id="ff91f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ff91f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ff91f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ff91f-108"> EDI</span></span>|  
|<span data-ttu-id="ff91f-109">组件</span><span class="sxs-lookup"><span data-stu-id="ff91f-109">Component</span></span>|<span data-ttu-id="ff91f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ff91f-110">EDI Engine</span></span>|  
|<span data-ttu-id="ff91f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ff91f-111">Symbolic Name</span></span>|<span data-ttu-id="ff91f-112">0</span><span class="sxs-lookup"><span data-stu-id="ff91f-112">0</span></span>|  
|<span data-ttu-id="ff91f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ff91f-113">Message Text</span></span>|<span data-ttu-id="ff91f-114">若要启用状态报告，请运行“BizTalk Server 配置”并配置 EDI/AS2 状态报告功能。 </span><span class="sxs-lookup"><span data-stu-id="ff91f-114">To enable status reporting, run 'BizTalk Server Configuration' and configure EDI/AS2 status reporting feature.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ff91f-115">解释</span><span class="sxs-lookup"><span data-stu-id="ff91f-115">Explanation</span></span>  
 <span data-ttu-id="ff91f-116">此错误/警告/信息事件指示，EDI/AS2 状态报告为不工作，因为尚未配置。</span><span class="sxs-lookup"><span data-stu-id="ff91f-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not working because it has not been configured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ff91f-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ff91f-117">User Action</span></span>  
 <span data-ttu-id="ff91f-118">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ff91f-118">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="ff91f-119">运行 BizTalk 服务器配置向导。</span><span class="sxs-lookup"><span data-stu-id="ff91f-119">Run the BizTalk Server Configuration wizard.</span></span> <span data-ttu-id="ff91f-120">单击 BizTalk EDI/AS2 运行时节点中，然后选中"启用 BizTalk EDI/AS2 运行时状态报告为此 BizTalk 组"属性。</span><span class="sxs-lookup"><span data-stu-id="ff91f-120">Click the BizTalk EDI/AS2 Runtime node, and check the "Enable BizTalk EDI/AS2 Runtime Status Reporting for this BizTalk Group" property.</span></span> <span data-ttu-id="ff91f-121">你必须配置 BAM，以便配置 EDI/AS2 状态报告。</span><span class="sxs-lookup"><span data-stu-id="ff91f-121">You must configure BAM in order to configure EDI/AS2 status reporting.</span></span>  
  
2.  <span data-ttu-id="ff91f-122">在 BizTalk Server 管理控制台中，启用 EDI 状态报告为方通过单击 EDI 属性对话框中的常规页中的"激活 EDI 报表"属性。</span><span class="sxs-lookup"><span data-stu-id="ff91f-122">In the BizTalk Server Administration Console, enable EDI status reporting for the party by clicking the "Activate EDI reporting" property in the General page of the EDI Properties dialog box.</span></span> <span data-ttu-id="ff91f-123">启用 AS2 状态报告为方通过单击 AS2 属性对话框中的常规页中的"激活 AS2 报表"属性。</span><span class="sxs-lookup"><span data-stu-id="ff91f-123">Enable AS2 status reporting for the party by clicking the "Activate AS2 reporting" property in the General page of the AS2 Properties dialog box.</span></span> <span data-ttu-id="ff91f-124">启用 EDI 或 AS2 状态报告后，必须重新启动 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="ff91f-124">You must restart the BizTalk service after enabling EDI or AS2 status reporting.</span></span>