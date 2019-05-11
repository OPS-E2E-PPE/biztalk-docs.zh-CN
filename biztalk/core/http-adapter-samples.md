---
title: HTTP 适配器示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1747a9bb28bc84dc0f6772435411d07557bf463e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383115"
---
# <a name="http-adapter-samples"></a><span data-ttu-id="f9110-102">HTTP 适配器示例</span><span class="sxs-lookup"><span data-stu-id="f9110-102">HTTP Adapter Samples</span></span>
<span data-ttu-id="f9110-103">本节包含演示使用 BizTalk HTTP 适配器时的高级的功能的示例。</span><span class="sxs-lookup"><span data-stu-id="f9110-103">This section contains samples that illustrate advanced functionality when using the BizTalk HTTP Adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9110-104">运行此示例之前，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f9110-104">Before running this sample, you need to do the following steps:</span></span>  
> 
> 1. <span data-ttu-id="f9110-105">打开 IIS，添加 ISAPI 和 CGI 限制：</span><span class="sxs-lookup"><span data-stu-id="f9110-105">Open IIS, add ISAPI and CGI restrictions:</span></span>  
> 
>    <span data-ttu-id="f9110-106">在左面板中，单击计算机名称，然后单击"ISAPI 和 CGI 限制"的右侧面板中，然后添加 ISAPI 或 CGI 路径：</span><span class="sxs-lookup"><span data-stu-id="f9110-106">Click Machine Name on left panel, then click "ISAPI and CGI restrictions" on the right panel, then Add the ISAPI or CGI path:</span></span>  
> 
>    <span data-ttu-id="f9110-107">在 64 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="f9110-107">On a 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="f9110-108">在 32 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="f9110-108">On a 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="f9110-109">检查允许的扩展路径或执行。</span><span class="sxs-lookup"><span data-stu-id="f9110-109">Check allowed extension path or execute.</span></span>  
>    2.  <span data-ttu-id="f9110-110">左面板中，单击"HTTPRequestResponseSample"，中间面板中，单击"处理程序映射"，然后单击"添加脚本映射"，使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="f9110-110">Click "HTTPRequestResponseSample" on left panel, then click "Handler Mapping" on middle panel, then click "Add script mapping” with the following setting:</span></span>  
> 
>    <span data-ttu-id="f9110-111">请求路径： btshttpreceive.dll</span><span class="sxs-lookup"><span data-stu-id="f9110-111">Request path:BTSHTTPReceive.dll</span></span>  
> 
>    <span data-ttu-id="f9110-112">可执行文件：</span><span class="sxs-lookup"><span data-stu-id="f9110-112">Executable:</span></span>  
> 
>    <span data-ttu-id="f9110-113">64 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\\</span><span class="sxs-lookup"><span data-stu-id="f9110-113">On 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\\</span></span>  
> 
>    <span data-ttu-id="f9110-114">在 32 位计算机上添加： C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\\</span><span class="sxs-lookup"><span data-stu-id="f9110-114">On 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\\</span></span>  
> 
>    <span data-ttu-id="f9110-115">请求限制：</span><span class="sxs-lookup"><span data-stu-id="f9110-115">Request restrictions:</span></span>  
> 
>    <span data-ttu-id="f9110-116">谓词：发布</span><span class="sxs-lookup"><span data-stu-id="f9110-116">Verbs: POST</span></span>  
> 
>    <span data-ttu-id="f9110-117">访问：脚本</span><span class="sxs-lookup"><span data-stu-id="f9110-117">Access: Script</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9110-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="f9110-118">In This Section</span></span>  
  
-   [<span data-ttu-id="f9110-119">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="f9110-119">HTTPSolicitResponse</span></span>](../core/httpsolicitresponse.md)  
  
-   [<span data-ttu-id="f9110-120">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="f9110-120">HTTPRequestResponse</span></span>](../core/httprequestresponse.md)