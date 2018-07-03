---
title: 无法识别的出站消息封送类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda3e7bd3d20e39bb59c2c1fbe14dfc964fd541a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023427"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a><span data-ttu-id="8585c-102">无法识别的出站消息封送类型</span><span class="sxs-lookup"><span data-stu-id="8585c-102">Unrecognized outbound message marshalling type</span></span>
## <a name="details"></a><span data-ttu-id="8585c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8585c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8585c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8585c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8585c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8585c-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    <span data-ttu-id="8585c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8585c-106">Event ID</span></span>     |                                           <span data-ttu-id="8585c-107">0</span><span class="sxs-lookup"><span data-stu-id="8585c-107">0</span></span>                                            |
|  <span data-ttu-id="8585c-108">事件源</span><span class="sxs-lookup"><span data-stu-id="8585c-108">Event Source</span></span>   |                                           <span data-ttu-id="8585c-109">0</span><span class="sxs-lookup"><span data-stu-id="8585c-109">0</span></span>                                            |
|    <span data-ttu-id="8585c-110">组件</span><span class="sxs-lookup"><span data-stu-id="8585c-110">Component</span></span>    |                                           <span data-ttu-id="8585c-111">0</span><span class="sxs-lookup"><span data-stu-id="8585c-111">0</span></span>                                            |
|  <span data-ttu-id="8585c-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="8585c-112">Symbolic Name</span></span>  |                                           <span data-ttu-id="8585c-113">0</span><span class="sxs-lookup"><span data-stu-id="8585c-113">0</span></span>                                            |
|  <span data-ttu-id="8585c-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="8585c-114">Message Text</span></span>   | <span data-ttu-id="8585c-115">无法识别的出站消息封送类型；应为 UseBodyElement 或 UseTemplate</span><span class="sxs-lookup"><span data-stu-id="8585c-115">Unrecognized outbound message marshalling type; expected UseBodyElement or UseTemplate</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8585c-116">解释</span><span class="sxs-lookup"><span data-stu-id="8585c-116">Explanation</span></span>  
 <span data-ttu-id="8585c-117">WCF。OutboundBodyLocation 属性设置为不同于为 UseBodyElement 或 UseTemplate，自定义管道组件或业务流程中的值。</span><span class="sxs-lookup"><span data-stu-id="8585c-117">The WCF.OutboundBodyLocation property is set to a value different than UseBodyElement or UseTemplate, in a custom pipeline component or orchestration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8585c-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8585c-118">User Action</span></span>  
 <span data-ttu-id="8585c-119">将 WCF.OutboundBodyLocation 属性设置为有效值。</span><span class="sxs-lookup"><span data-stu-id="8585c-119">Set the WCF.OutboundBodyLocation property to a valid value.</span></span> <span data-ttu-id="8585c-120">有效值为“UseBodyElement”或“UseTemplate”。这是代码更改。</span><span class="sxs-lookup"><span data-stu-id="8585c-120">Valid values are "UseBodyElement" or "UseTemplate" This is a code change.</span></span>   
<span data-ttu-id="8585c-121">有关出站消息的进一步信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="8585c-121">For further information about outbound messaging, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="8585c-122">使用 WCF 适配器上下文属性配置动态发送端口</span><span class="sxs-lookup"><span data-stu-id="8585c-122">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="8585c-123">配置 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="8585c-123">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)