---
title: 发送端口中没有匹配的转换找到 DocType |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc45ac0edf425bc19ab526fac6b2690f3a6b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263053"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a><span data-ttu-id="68550-102">发送端口中找不到与 DocType 匹配的转换</span><span class="sxs-lookup"><span data-stu-id="68550-102">No matching transform found for DocType in Send Port</span></span>
## <a name="details"></a><span data-ttu-id="68550-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="68550-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68550-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="68550-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="68550-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="68550-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="68550-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="68550-106">Event ID</span></span>|-|  
|<span data-ttu-id="68550-107">事件源</span><span class="sxs-lookup"><span data-stu-id="68550-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="68550-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="68550-108"> EDI</span></span>|  
|<span data-ttu-id="68550-109">组件</span><span class="sxs-lookup"><span data-stu-id="68550-109">Component</span></span>|<span data-ttu-id="68550-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="68550-110">EDI Engine</span></span>|  
|<span data-ttu-id="68550-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="68550-111">Symbolic Name</span></span>|<span data-ttu-id="68550-112">NoMatchingTransformFoundForSendPortAndDocType</span><span class="sxs-lookup"><span data-stu-id="68550-112">NoMatchingTransformFoundForSendPortAndDocType</span></span>|  
|<span data-ttu-id="68550-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="68550-113">Message Text</span></span>|<span data-ttu-id="68550-114">未找到中发送端口 {1} DocType {0} 的匹配的转换。</span><span class="sxs-lookup"><span data-stu-id="68550-114">No matching transform found for DocType {0} in Send Port {1}.</span></span> <span data-ttu-id="68550-115">与 ExplorerOM 信息不一致</span><span class="sxs-lookup"><span data-stu-id="68550-115">Inconsistent with ExplorerOM information</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68550-116">解释</span><span class="sxs-lookup"><span data-stu-id="68550-116">Explanation</span></span>  
 <span data-ttu-id="68550-117">此错误表明没有为给定的 DocType 和 SendPort 找到匹配的转换。</span><span class="sxs-lookup"><span data-stu-id="68550-117">This error indicates that a matching transform was not found for a given DocType and SendPort.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68550-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="68550-118">User Action</span></span>  
 <span data-ttu-id="68550-119">若要解决此错误，请继续执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="68550-119">To resolve this error, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="68550-120">打开 BizTalk 管理控制台，找到传输并右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="68550-120">Open the BizTalk Administration console, locate the transport, and right-click the transport name.</span></span>  
  
2.  <span data-ttu-id="68550-121">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="68550-121">Click **Properties**.</span></span>  
  
3.  <span data-ttu-id="68550-122">在端口类型列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="68550-122">In the port Type list, select the correct port.</span></span> <span data-ttu-id="68550-123">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="68550-123">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="68550-124">在 [端口名称] 发送端口属性对话框中，单击**出站映射**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="68550-124">In the [port name] Send Port Properties dialog box, click **Outbound Maps** in the left pane.</span></span>  
  
5.  <span data-ttu-id="68550-125">验证此处是否列出了映射以及该映射是否与正确的文档类型相对应。</span><span class="sxs-lookup"><span data-stu-id="68550-125">Verify that the map is listed here and that it corresponds to the correct document type.</span></span>