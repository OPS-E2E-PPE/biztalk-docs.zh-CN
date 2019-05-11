---
title: 创建 Web 服务和 Web 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, schemas
- orchestrations, naming conventions
- Web services, naming conventions
- schemas, Web services
ms.assetid: a7c47000-501c-47b1-bafa-82370585c1db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22d93635ce23f4ce8899f3d9f6d95dfca2010ea7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389858"
---
# <a name="creating-web-services-and-web-methods"></a><span data-ttu-id="853e2-102">创建 Web 服务和 Web 方法</span><span class="sxs-lookup"><span data-stu-id="853e2-102">Creating Web Services and Web Methods</span></span>
<span data-ttu-id="853e2-103">时将架构发布为 Web 服务，可以控制创建的 Web 服务和 BizTalk Web Services 发布向导中的 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="853e2-103">When you publish schemas as a Web service, you control the creation of Web services and Web methods in the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="853e2-104">您可以重命名 Web 服务说明、 Web 服务和树视图中的 Web 服务页上的 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="853e2-104">You can rename the Web service description, Web service and Web method inside the tree available on the Web Services page.</span></span> <span data-ttu-id="853e2-105">您可以添加和删除 Web services 和 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="853e2-105">You can add and remove Web services and Web methods.</span></span> <span data-ttu-id="853e2-106">该向导使用选定的请求架构的根元素名称作为输入的参数名称。</span><span class="sxs-lookup"><span data-stu-id="853e2-106">The wizard uses the root element names of the selected request schemas as the input parameter name.</span></span> <span data-ttu-id="853e2-107">Web 方法返回值会返回响应架构。</span><span class="sxs-lookup"><span data-stu-id="853e2-107">The Web method return value returns the response schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="853e2-108">ASP.NET Web 客户端可能更改的组合 in 和 out 参数相同类型的 Web 方法签名。</span><span class="sxs-lookup"><span data-stu-id="853e2-108">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="853e2-109">例如，ASP.NET Web 客户端可能会更改 BizTalk Web 方法从**myService （字符串一部分） 的字符串**到**void myService （ref 字符串一部分）**。</span><span class="sxs-lookup"><span data-stu-id="853e2-109">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="853e2-110">如果在接收端口已定义为单向，则 Web 方法响应类型为**void**和到 Web 客户端返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="853e2-110">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="853e2-111">SOAP 适配器和业务流程不会返回引发的异常到 Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="853e2-111">The SOAP adapter and orchestration do not return thrown exceptions to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="853e2-112">Web services 已发布的业务流程的命名的约定</span><span class="sxs-lookup"><span data-stu-id="853e2-112">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="853e2-113">BizTalk Web Services 发布向导生成基于 Web 服务页中定义的 Web 服务说明的 Web 服务 (.asmx) 文件名。</span><span class="sxs-lookup"><span data-stu-id="853e2-113">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the Web services description that you define in the Web Service page.</span></span> <span data-ttu-id="853e2-114">下表显示了 Web 服务文件名称的默认值。</span><span class="sxs-lookup"><span data-stu-id="853e2-114">The following table shows the default values for the Web service file names.</span></span>  
  
|<span data-ttu-id="853e2-115">生成的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="853e2-115">Generated Web service</span></span>|<span data-ttu-id="853e2-116">File name</span><span class="sxs-lookup"><span data-stu-id="853e2-116">File name</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="853e2-117">BizTalkWebService</span><span class="sxs-lookup"><span data-stu-id="853e2-117">BizTalkWebService</span></span>|<span data-ttu-id="853e2-118">Visual Studio Web 服务项目的名称</span><span class="sxs-lookup"><span data-stu-id="853e2-118">Visual Studio Web Service project name</span></span>|  
|<span data-ttu-id="853e2-119">WebService1</span><span class="sxs-lookup"><span data-stu-id="853e2-119">WebService1</span></span>|<span data-ttu-id="853e2-120">Web 服务 (.asmx) 文件名</span><span class="sxs-lookup"><span data-stu-id="853e2-120">Web service (.asmx) file name</span></span>|  
|<span data-ttu-id="853e2-121">WebMethod1</span><span class="sxs-lookup"><span data-stu-id="853e2-121">WebMethod1</span></span>|<span data-ttu-id="853e2-122">Web 方法名称</span><span class="sxs-lookup"><span data-stu-id="853e2-122">Web method name</span></span>|  
  
 <span data-ttu-id="853e2-123">生成的 Web 服务不反映其余节点的名称。</span><span class="sxs-lookup"><span data-stu-id="853e2-123">The generated Web service does not reflect the names of the remaining nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="853e2-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="853e2-124">See Also</span></span>  
 <span data-ttu-id="853e2-125">[将架构发布为 Web 服务](../core/publishing-schemas-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="853e2-125">[Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="853e2-126">如何使用 BizTalk Web Services 发布向导将架构发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="853e2-126">How to Use the BizTalk Web Services Publishing Wizard to Publish Schemas as a Web Service</span></span>](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)