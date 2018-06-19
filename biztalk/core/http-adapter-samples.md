---
title: HTTP 适配器示例 |Microsoft 文档
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
ms.openlocfilehash: a1111322d59f8ff5c6ba6209aa48eb515a23c72f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970979"
---
# <a name="http-adapter-samples"></a><span data-ttu-id="ebaea-102">HTTP 适配器示例</span><span class="sxs-lookup"><span data-stu-id="ebaea-102">HTTP Adapter Samples</span></span>
<span data-ttu-id="ebaea-103">本部分中包含的示例演示 BizTalk HTTP 适配器的高级功能。</span><span class="sxs-lookup"><span data-stu-id="ebaea-103">This section contains samples that illustrate advanced functionality when using the BizTalk HTTP Adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebaea-104">在运行此示例之前，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ebaea-104">Before running this sample, you need to do the following steps:</span></span>  
>   
>  1.  <span data-ttu-id="ebaea-105">打开 IIS，添加 ISAPI 和 CGI 限制：</span><span class="sxs-lookup"><span data-stu-id="ebaea-105">Open IIS, add ISAPI and CGI restrictions:</span></span>  
>   
>      <span data-ttu-id="ebaea-106">单击左侧面板中的计算机名称，再单击右侧面板中的“ISAPI 和 CGI 限制”，然后添加 ISAPI 或 CGI 路径：</span><span class="sxs-lookup"><span data-stu-id="ebaea-106">Click Machine Name on left panel, then click "ISAPI and CGI restrictions" on the right panel, then Add the ISAPI or CGI path:</span></span>  
>   
>      <span data-ttu-id="ebaea-107">在 64 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\HttpReceive64\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="ebaea-107">On a 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="ebaea-108">在 32 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\HttpReceive\BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="ebaea-108">On a 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="ebaea-109">检查允许的扩展路径或执行。</span><span class="sxs-lookup"><span data-stu-id="ebaea-109">Check allowed extension path or execute.</span></span>  
> 2.  <span data-ttu-id="ebaea-110">单击左侧面板中的“HTTPRequestResponseSample”，再单击中间面板中的“处理程序映射”，然后单击“添加脚本映射”并进行以下设置：</span><span class="sxs-lookup"><span data-stu-id="ebaea-110">Click "HTTPRequestResponseSample" on left panel, then click "Handler Mapping" on middle panel, then click "Add script mapping” with the following setting:</span></span>  
>   
>      <span data-ttu-id="ebaea-111">请求路径：BTSHTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="ebaea-111">Request path:BTSHTTPReceive.dll</span></span>  
>   
>      <span data-ttu-id="ebaea-112">可执行文件：</span><span class="sxs-lookup"><span data-stu-id="ebaea-112">Executable:</span></span>  
>   
>      <span data-ttu-id="ebaea-113">在 64 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\HttpReceive64\\</span><span class="sxs-lookup"><span data-stu-id="ebaea-113">On 64 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\\</span></span>  
>   
>      <span data-ttu-id="ebaea-114">在 32 位计算机上添加： C:\Program Files (x86) \Microsoft BizTalk Server\<版本\>\HttpReceive\\</span><span class="sxs-lookup"><span data-stu-id="ebaea-114">On 32 bit machine add:   C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\\</span></span>  
>   
>      <span data-ttu-id="ebaea-115">请求限制：</span><span class="sxs-lookup"><span data-stu-id="ebaea-115">Request restrictions:</span></span>  
>   
>      <span data-ttu-id="ebaea-116">谓词： POST</span><span class="sxs-lookup"><span data-stu-id="ebaea-116">Verbs: POST</span></span>  
>   
>      <span data-ttu-id="ebaea-117">访问： 脚本</span><span class="sxs-lookup"><span data-stu-id="ebaea-117">Access: Script</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebaea-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="ebaea-118">In This Section</span></span>  
  
-   [<span data-ttu-id="ebaea-119">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="ebaea-119">HTTPSolicitResponse</span></span>](../core/httpsolicitresponse.md)  
  
-   [<span data-ttu-id="ebaea-120">HTTPRequestResponse</span><span class="sxs-lookup"><span data-stu-id="ebaea-120">HTTPRequestResponse</span></span>](../core/httprequestresponse.md)