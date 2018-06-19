---
title: 创建 Web 服务和 Web 方法 |Microsoft 文档
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
ms.openlocfilehash: 74065489e427ae0612897f1f333e3c8e154a535f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238381"
---
# <a name="creating-web-services-and-web-methods"></a><span data-ttu-id="cacb3-102">创建 Web 服务和 Web 方法</span><span class="sxs-lookup"><span data-stu-id="cacb3-102">Creating Web Services and Web Methods</span></span>
<span data-ttu-id="cacb3-103">在将架构发布为 Web Services 时，您可在 BizTalk Web Services 发布向导中控制 Web Services 和 Web 方法的创建。</span><span class="sxs-lookup"><span data-stu-id="cacb3-103">When you publish schemas as a Web service, you control the creation of Web services and Web methods in the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="cacb3-104">您可以重命名 Web Services 页上树视图中的 Web Services 说明、Web Services 和 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="cacb3-104">You can rename the Web service description, Web service and Web method inside the tree available on the Web Services page.</span></span> <span data-ttu-id="cacb3-105">可以添加和删除 Web Services 和 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="cacb3-105">You can add and remove Web services and Web methods.</span></span> <span data-ttu-id="cacb3-106">该向导使用选定请求架构的根元素名称作为输入参数名称。</span><span class="sxs-lookup"><span data-stu-id="cacb3-106">The wizard uses the root element names of the selected request schemas as the input parameter name.</span></span> <span data-ttu-id="cacb3-107">Web 方法返回值会返回响应架构。</span><span class="sxs-lookup"><span data-stu-id="cacb3-107">The Web method return value returns the response schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cacb3-108">ASP.NET Web 客户端可以通过合并相同类型的 in 参数和 out 参数更改 Web 方法签名。</span><span class="sxs-lookup"><span data-stu-id="cacb3-108">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="cacb3-109">例如，ASP.NET Web 客户端可能会更改从某一 BizTalk Web 方法**字符串 myService （字符串一部分）** 到**void myService （ref 字符串一部分）**。</span><span class="sxs-lookup"><span data-stu-id="cacb3-109">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cacb3-110">如果你收到定义端口，则为单向，Web 方法的响应类型是**void**和 Web 客户端返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="cacb3-110">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="cacb3-111">SOAP 适配器和业务流程不会将引发的异常返回到 Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="cacb3-111">The SOAP adapter and orchestration do not return thrown exceptions to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="cacb3-112">已发布业务流程的 Web Services 命名约定</span><span class="sxs-lookup"><span data-stu-id="cacb3-112">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="cacb3-113">BizTalk Web Services 发布向导基于在 Web Services 页中定义的 Web Services 说明生成 Web Services (.asmx) 文件名。</span><span class="sxs-lookup"><span data-stu-id="cacb3-113">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the Web services description that you define in the Web Service page.</span></span> <span data-ttu-id="cacb3-114">下表显示了 Web Services 文件名的默认值。</span><span class="sxs-lookup"><span data-stu-id="cacb3-114">The following table shows the default values for the Web service file names.</span></span>  
  
|<span data-ttu-id="cacb3-115">生成的 Web Services</span><span class="sxs-lookup"><span data-stu-id="cacb3-115">Generated Web service</span></span>|<span data-ttu-id="cacb3-116">文件名</span><span class="sxs-lookup"><span data-stu-id="cacb3-116">File name</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="cacb3-117">BizTalkWebService</span><span class="sxs-lookup"><span data-stu-id="cacb3-117">BizTalkWebService</span></span>|<span data-ttu-id="cacb3-118">Visual Studio Web Services 项目名称</span><span class="sxs-lookup"><span data-stu-id="cacb3-118">Visual Studio Web Service project name</span></span>|  
|<span data-ttu-id="cacb3-119">WebService1</span><span class="sxs-lookup"><span data-stu-id="cacb3-119">WebService1</span></span>|<span data-ttu-id="cacb3-120">Web Services (.asmx) 文件名</span><span class="sxs-lookup"><span data-stu-id="cacb3-120">Web service (.asmx) file name</span></span>|  
|<span data-ttu-id="cacb3-121">WebMethod1</span><span class="sxs-lookup"><span data-stu-id="cacb3-121">WebMethod1</span></span>|<span data-ttu-id="cacb3-122">Web 方法名</span><span class="sxs-lookup"><span data-stu-id="cacb3-122">Web method name</span></span>|  
  
 <span data-ttu-id="cacb3-123">生成的 Web Services 不反映其余节点的名称。</span><span class="sxs-lookup"><span data-stu-id="cacb3-123">The generated Web service does not reflect the names of the remaining nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacb3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cacb3-124">See Also</span></span>  
 <span data-ttu-id="cacb3-125">[发布架构作为 Web 服务](../core/publishing-schemas-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cacb3-125">[Publishing Schemas as a Web Service](../core/publishing-schemas-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="cacb3-126">如何使用发布向导的 BizTalk Web 服务以将架构作为 Web 服务发布</span><span class="sxs-lookup"><span data-stu-id="cacb3-126">How to Use the BizTalk Web Services Publishing Wizard to Publish Schemas as a Web Service</span></span>](../core/publish-schemas-as-web-services-with-biztalk-web-services-publishing-wizard.md)