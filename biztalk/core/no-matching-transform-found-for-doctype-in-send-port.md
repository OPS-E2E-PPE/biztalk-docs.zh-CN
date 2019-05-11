---
title: 发送端口中找到 DocType 为没有匹配的转换 |Microsoft Docs
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
ms.openlocfilehash: fd58b772afe9695d526038f622d968c75b75d252
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263404"
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a><span data-ttu-id="2c320-102">发送端口中找到 DocType 不匹配转换</span><span class="sxs-lookup"><span data-stu-id="2c320-102">No matching transform found for DocType in Send Port</span></span>
## <a name="details"></a><span data-ttu-id="2c320-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2c320-103">Details</span></span>  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2c320-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2c320-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="2c320-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2c320-105">Product Version</span></span> |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="2c320-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2c320-106">Event ID</span></span>     |                                                   -                                                    |
|  <span data-ttu-id="2c320-107">事件源</span><span class="sxs-lookup"><span data-stu-id="2c320-107">Event Source</span></span>   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2c320-108">EDI</span><span class="sxs-lookup"><span data-stu-id="2c320-108">EDI</span></span>         |
|    <span data-ttu-id="2c320-109">组件</span><span class="sxs-lookup"><span data-stu-id="2c320-109">Component</span></span>    |                                               <span data-ttu-id="2c320-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="2c320-110">EDI Engine</span></span>                                               |
|  <span data-ttu-id="2c320-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="2c320-111">Symbolic Name</span></span>  |                             <span data-ttu-id="2c320-112">NoMatchingTransformFoundForSendPortAndDocType</span><span class="sxs-lookup"><span data-stu-id="2c320-112">NoMatchingTransformFoundForSendPortAndDocType</span></span>                              |
|  <span data-ttu-id="2c320-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="2c320-113">Message Text</span></span>   | <span data-ttu-id="2c320-114">不匹配转换找到 DocType{0}发送端口中{1}。</span><span class="sxs-lookup"><span data-stu-id="2c320-114">No matching transform found for DocType {0} in Send Port {1}.</span></span> <span data-ttu-id="2c320-115">与 ExplorerOM 信息不一致</span><span class="sxs-lookup"><span data-stu-id="2c320-115">Inconsistent with ExplorerOM information</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2c320-116">解释</span><span class="sxs-lookup"><span data-stu-id="2c320-116">Explanation</span></span>  
 <span data-ttu-id="2c320-117">此错误指示不为给定的 DocType 和 SendPort 找到匹配的转换。</span><span class="sxs-lookup"><span data-stu-id="2c320-117">This error indicates that a matching transform was not found for a given DocType and SendPort.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2c320-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="2c320-118">User Action</span></span>  
 <span data-ttu-id="2c320-119">若要解决此错误，请继续阅读，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2c320-119">To resolve this error, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="2c320-120">打开 BizTalk 管理控制台中，找到传输并右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="2c320-120">Open the BizTalk Administration console, locate the transport, and right-click the transport name.</span></span>  
  
2.  <span data-ttu-id="2c320-121">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="2c320-121">Click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2c320-122">在端口类型列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="2c320-122">In the port Type list, select the correct port.</span></span> <span data-ttu-id="2c320-123">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="2c320-123">Click **Configure**.</span></span>  
  
4.  <span data-ttu-id="2c320-124">在 [端口名称] 发送端口属性对话框中，单击**出站映射**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="2c320-124">In the [port name] Send Port Properties dialog box, click **Outbound Maps** in the left pane.</span></span>  
  
5.  <span data-ttu-id="2c320-125">验证此处列出了映射以及它对应于正确的文档类型。</span><span class="sxs-lookup"><span data-stu-id="2c320-125">Verify that the map is listed here and that it corresponds to the correct document type.</span></span>