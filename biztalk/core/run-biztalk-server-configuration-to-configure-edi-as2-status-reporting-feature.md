---
title: 若要启用状态报告，请运行&#39;BizTalk Server 配置&#39;并配置 EDI-AS2 状态报告功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf125919-80ab-4cb8-b1f5-0f2616cc6f5c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89d7fcf5e473485d0b61edcd6d5f287198021d3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992710"
---
# <a name="to-enable-status-reporting-run-39biztalk-server-configuration39-and-configure-edi-as2-status-reporting-feature"></a><span data-ttu-id="e680f-102">若要启用状态报告，请运行&#39;BizTalk Server 配置&#39;并配置 EDI-AS2 状态报告功能</span><span class="sxs-lookup"><span data-stu-id="e680f-102">To enable status reporting, run &#39;BizTalk Server Configuration&#39; and configure EDI-AS2 status reporting feature</span></span>
## <a name="details"></a><span data-ttu-id="e680f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e680f-103">Details</span></span>  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e680f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e680f-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="e680f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e680f-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="e680f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e680f-106">Event ID</span></span>     |                                                       -                                                        |
|  <span data-ttu-id="e680f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e680f-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e680f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e680f-108"> EDI</span></span>             |
|    <span data-ttu-id="e680f-109">组件</span><span class="sxs-lookup"><span data-stu-id="e680f-109">Component</span></span>    |                                                   <span data-ttu-id="e680f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e680f-110">EDI Engine</span></span>                                                   |
|  <span data-ttu-id="e680f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e680f-111">Symbolic Name</span></span>  |                                                       <span data-ttu-id="e680f-112">0</span><span class="sxs-lookup"><span data-stu-id="e680f-112">0</span></span>                                                        |
|  <span data-ttu-id="e680f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e680f-113">Message Text</span></span>   | <span data-ttu-id="e680f-114">若要启用状态报告，请运行“BizTalk Server 配置”并配置 EDI/AS2 状态报告功能。 </span><span class="sxs-lookup"><span data-stu-id="e680f-114">To enable status reporting, run 'BizTalk Server Configuration' and configure EDI/AS2 status reporting feature.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e680f-115">解释</span><span class="sxs-lookup"><span data-stu-id="e680f-115">Explanation</span></span>  
 <span data-ttu-id="e680f-116">此错误/警告/信息事件表明，EDI/AS2 状态报告为不工作，因为尚未配置。</span><span class="sxs-lookup"><span data-stu-id="e680f-116">This Error/Warning/Information event indicates that EDI/AS2 status reporting is not working because it has not been configured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e680f-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e680f-117">User Action</span></span>  
 <span data-ttu-id="e680f-118">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e680f-118">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="e680f-119">运行 BizTalk Server 配置向导。</span><span class="sxs-lookup"><span data-stu-id="e680f-119">Run the BizTalk Server Configuration wizard.</span></span> <span data-ttu-id="e680f-120">单击 BizTalk EDI/AS2 运行时节点中，然后选中"启用 BizTalk EDI/AS2 运行时状态报告为此 BizTalk 组"属性。</span><span class="sxs-lookup"><span data-stu-id="e680f-120">Click the BizTalk EDI/AS2 Runtime node, and check the "Enable BizTalk EDI/AS2 Runtime Status Reporting for this BizTalk Group" property.</span></span> <span data-ttu-id="e680f-121">若要配置 EDI/AS2 状态报告，必须配置 BAM。</span><span class="sxs-lookup"><span data-stu-id="e680f-121">You must configure BAM in order to configure EDI/AS2 status reporting.</span></span>  
  
2.  <span data-ttu-id="e680f-122">在 BizTalk Server 管理控制台中，启用 EDI 状态报告功能的参与方，单击 EDI 属性对话框的常规页中的"激活 EDI 报告"属性。</span><span class="sxs-lookup"><span data-stu-id="e680f-122">In the BizTalk Server Administration Console, enable EDI status reporting for the party by clicking the "Activate EDI reporting" property in the General page of the EDI Properties dialog box.</span></span> <span data-ttu-id="e680f-123">启用 AS2 状态报告功能的参与方，单击 AS2 属性对话框的常规页中的"激活 AS2 报告"属性。</span><span class="sxs-lookup"><span data-stu-id="e680f-123">Enable AS2 status reporting for the party by clicking the "Activate AS2 reporting" property in the General page of the AS2 Properties dialog box.</span></span> <span data-ttu-id="e680f-124">启用 EDI 或 AS2 状态报告后，必须重新启动 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="e680f-124">You must restart the BizTalk service after enabling EDI or AS2 status reporting.</span></span>