---
title: "BTSWebSvcPub 命令行参考 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e19dd4d-9f2c-4a17-9437-8701e1c274fb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9993092c0d798ae2d47f614a24da21c3a2df62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btswebsvcpub-command-line-reference"></a><span data-ttu-id="f0064-102">BTSWebSvcPub 命令行参考</span><span class="sxs-lookup"><span data-stu-id="f0064-102">BTSWebSvcPub Command-Line Reference</span></span>
<span data-ttu-id="f0064-103">本主题提供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含的 BTSWebSvcPub 命令行工具的参考信息。</span><span class="sxs-lookup"><span data-stu-id="f0064-103">This topic provides reference information for the BTSWebSvcPub command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f0064-104">您可以使用 BTSWebSvcPub 创建 Web Services (.asmx)，以通过 Web Services 发布业务流程，BTSWebSvcPub 的具体用法如下：</span><span class="sxs-lookup"><span data-stu-id="f0064-104">You can use BTSWebSvcPub to create Web services (.asmx) for publishing orchestrations through Web services as follows:</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f0064-105">用法</span><span class="sxs-lookup"><span data-stu-id="f0064-105">Usage</span></span>  
 <span data-ttu-id="f0064-106">**BTSWebSvcPub 路径名 [-位置：** *值* **] [-覆盖] [-匿名]**</span><span class="sxs-lookup"><span data-stu-id="f0064-106">**BTSWebSvcPub PathName [-Location:** *value* **] [-Overwrite] [-Anonymous]**</span></span>  
  
 <span data-ttu-id="f0064-107">**[-名称：** *值* **] [-Namespace:** *值* **] [-TargetNamespace:** *值* **]**</span><span class="sxs-lookup"><span data-stu-id="f0064-107">**[-Name:** *value* **] [-Namespace:** *value* **] [-TargetNamespace:** *value* **]**</span></span>  
  
 <span data-ttu-id="f0064-108">**[-UnknownHeaders [**  *+*  **&#124;** *-*  **]] [-单一登录 [**  *+*  **&#124;** *-*  **]] [-ParameterStyle:** *值* **]**</span><span class="sxs-lookup"><span data-stu-id="f0064-108">**[-UnknownHeaders[** *+* **&#124;** *-* **]] [-SingleSignOn[** *+* **&#124;** *-* **]] [-ParameterStyle:** *value* **]**</span></span>  
  
 <span data-ttu-id="f0064-109">**[-ConformanceClaims:** *值* **] [-ForceRequestResponse:** *值* **] [-接收位置]**</span><span class="sxs-lookup"><span data-stu-id="f0064-109">**[-ConformanceClaims:** *value* **] [-ForceRequestResponse:** *value* **] [-ReceiveLocation]**</span></span>  
  
 <span data-ttu-id="f0064-110">**[-ApplicationName:** *值* **]**</span><span class="sxs-lookup"><span data-stu-id="f0064-110">**[-ApplicationName:** *value* **]**</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="f0064-111">Parameters</span><span class="sxs-lookup"><span data-stu-id="f0064-111">Parameters</span></span>  
  
|<span data-ttu-id="f0064-112">参数</span><span class="sxs-lookup"><span data-stu-id="f0064-112">Parameter</span></span>|<span data-ttu-id="f0064-113">必需</span><span class="sxs-lookup"><span data-stu-id="f0064-113">Required</span></span>|<span data-ttu-id="f0064-114">Description</span><span class="sxs-lookup"><span data-stu-id="f0064-114">Description</span></span>|  
|---------------|--------------|-----------------|  
|<span data-ttu-id="f0064-115">**PathName**</span><span class="sxs-lookup"><span data-stu-id="f0064-115">**PathName**</span></span>|<span data-ttu-id="f0064-116">是</span><span class="sxs-lookup"><span data-stu-id="f0064-116">Yes</span></span>|<span data-ttu-id="f0064-117">BizTalk 程序集 (*.dll) 或 web 服务描述的路径和文件名称 (\*.xml) 文件。</span><span class="sxs-lookup"><span data-stu-id="f0064-117">Path and file name of BizTalk assembly (*.dll) or web service description (\*.xml) file.</span></span>|  
|<span data-ttu-id="f0064-118">**位置**</span><span class="sxs-lookup"><span data-stu-id="f0064-118">**-Location**</span></span>|<span data-ttu-id="f0064-119">是</span><span class="sxs-lookup"><span data-stu-id="f0064-119">No</span></span>|<span data-ttu-id="f0064-120">要发布到的目标位置。</span><span class="sxs-lookup"><span data-stu-id="f0064-120">Location in which to publish.</span></span> <span data-ttu-id="f0064-121">(语法:"http://host [: 端口] / 路径")</span><span class="sxs-lookup"><span data-stu-id="f0064-121">(Syntax:"http://host[:port]/path")</span></span>|  
|<span data-ttu-id="f0064-122">**-覆盖**</span><span class="sxs-lookup"><span data-stu-id="f0064-122">**-Overwrite**</span></span>|<span data-ttu-id="f0064-123">是</span><span class="sxs-lookup"><span data-stu-id="f0064-123">No</span></span>|<span data-ttu-id="f0064-124">覆盖指定的位置。</span><span class="sxs-lookup"><span data-stu-id="f0064-124">Overwrite specified location.</span></span>|  
|<span data-ttu-id="f0064-125">**匿名**</span><span class="sxs-lookup"><span data-stu-id="f0064-125">**-Anonymous**</span></span>|<span data-ttu-id="f0064-126">是</span><span class="sxs-lookup"><span data-stu-id="f0064-126">No</span></span>|<span data-ttu-id="f0064-127">允许匿名访问 Web Services。</span><span class="sxs-lookup"><span data-stu-id="f0064-127">Allow anonymous access to Web service.</span></span>|  
|<span data-ttu-id="f0064-128">**-名称**</span><span class="sxs-lookup"><span data-stu-id="f0064-128">**-Name**</span></span>|<span data-ttu-id="f0064-129">是</span><span class="sxs-lookup"><span data-stu-id="f0064-129">No</span></span>|<span data-ttu-id="f0064-130">将要包含该 Web Services 的解决方案和程序集（.sln 文件和 .dll 文件）的名称。</span><span class="sxs-lookup"><span data-stu-id="f0064-130">Name of the solution and assembly (.sln and .dll files) that will contain the Web service.</span></span>|  
|<span data-ttu-id="f0064-131">**-Namespace**</span><span class="sxs-lookup"><span data-stu-id="f0064-131">**-Namespace**</span></span>|<span data-ttu-id="f0064-132">是</span><span class="sxs-lookup"><span data-stu-id="f0064-132">No</span></span>|<span data-ttu-id="f0064-133">Web Services 代码的默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="f0064-133">Default namespace for Web service code.</span></span>|  
|<span data-ttu-id="f0064-134">**-Targetnamespace**</span><span class="sxs-lookup"><span data-stu-id="f0064-134">**-Targetnamespace**</span></span>|<span data-ttu-id="f0064-135">是</span><span class="sxs-lookup"><span data-stu-id="f0064-135">No</span></span>|<span data-ttu-id="f0064-136">Web Services 的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="f0064-136">Target namespace of the Web service.</span></span> <span data-ttu-id="f0064-137">（示例：“http://www.northwindtraders.com”）</span><span class="sxs-lookup"><span data-stu-id="f0064-137">(Example:'http://www.northwindtraders.com')</span></span>|  
|<span data-ttu-id="f0064-138">**-UnknownHeaders**</span><span class="sxs-lookup"><span data-stu-id="f0064-138">**-UnknownHeaders**</span></span>|<span data-ttu-id="f0064-139">是</span><span class="sxs-lookup"><span data-stu-id="f0064-139">No</span></span>|<span data-ttu-id="f0064-140">支持未知的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="f0064-140">Support unknown SOAP headers.</span></span>|  
|<span data-ttu-id="f0064-141">**-SinglesSignon**</span><span class="sxs-lookup"><span data-stu-id="f0064-141">**-SinglesSignon**</span></span>|<span data-ttu-id="f0064-142">是</span><span class="sxs-lookup"><span data-stu-id="f0064-142">No</span></span>|<span data-ttu-id="f0064-143">支持 SharePoint Portal Server 单一登录 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="f0064-143">Support SharePoint Portal Server Single Sign-On SOAP headers.</span></span>|  
|<span data-ttu-id="f0064-144">**-ParameterStyle**</span><span class="sxs-lookup"><span data-stu-id="f0064-144">**-ParameterStyle**</span></span>|<span data-ttu-id="f0064-145">是</span><span class="sxs-lookup"><span data-stu-id="f0064-145">No</span></span>|<span data-ttu-id="f0064-146">消息 SoapParameterStyle:"默认"、"裸机"或"换行"。</span><span class="sxs-lookup"><span data-stu-id="f0064-146">The SoapParameterStyle for messages: "Default", "Bare",or "Wrapped".</span></span>|  
|<span data-ttu-id="f0064-147">**-ConfirmanceClaims**</span><span class="sxs-lookup"><span data-stu-id="f0064-147">**-ConfirmanceClaims**</span></span>|<span data-ttu-id="f0064-148">是</span><span class="sxs-lookup"><span data-stu-id="f0064-148">No</span></span>|<span data-ttu-id="f0064-149">Web 服务互操作性 (WSI) 声明:"None"或"BasicProfile1_1"。</span><span class="sxs-lookup"><span data-stu-id="f0064-149">Web services interoperability (WSI) claim: "None" or"BasicProfile1_1".</span></span>|  
|<span data-ttu-id="f0064-150">**-ForceRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="f0064-150">**-ForceRequestResponse**</span></span>|<span data-ttu-id="f0064-151">是</span><span class="sxs-lookup"><span data-stu-id="f0064-151">No</span></span>|<span data-ttu-id="f0064-152">将单向 BizTalk 操作做为请求-响应 Web 方法公开。</span><span class="sxs-lookup"><span data-stu-id="f0064-152">Expose one-way BizTalk operations as request-response web methods.</span></span>|  
|<span data-ttu-id="f0064-153">**-接收位置**</span><span class="sxs-lookup"><span data-stu-id="f0064-153">**-ReceiveLocation**</span></span>|<span data-ttu-id="f0064-154">是</span><span class="sxs-lookup"><span data-stu-id="f0064-154">No</span></span>|<span data-ttu-id="f0064-155">在指定 BizTalk 应用程序中创建接收位置。</span><span class="sxs-lookup"><span data-stu-id="f0064-155">Create receive locations in the specified BizTalk application.</span></span>|  
|<span data-ttu-id="f0064-156">**-应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="f0064-156">**-ApplicationName**</span></span>|<span data-ttu-id="f0064-157">是</span><span class="sxs-lookup"><span data-stu-id="f0064-157">No</span></span>|<span data-ttu-id="f0064-158">要在其中创建接收位置的 BizTalk 应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="f0064-158">Name of the BizTalk application in which to create receive locations.</span></span> <span data-ttu-id="f0064-159">如果未指定，则使用默认 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0064-159">If not specified, the default BizTalk application is used.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="f0064-160">示例</span><span class="sxs-lookup"><span data-stu-id="f0064-160">Sample</span></span>  
 <span data-ttu-id="f0064-161">BTSWebSvcPub.exe"MyAssembly.dll"的位置： http://localhost/MyVdir</span><span class="sxs-lookup"><span data-stu-id="f0064-161">BTSWebSvcPub.exe "MyAssembly.dll" -Location:http://localhost/MyVdir</span></span>  
  
 <span data-ttu-id="f0064-162">-Overwrite</span><span class="sxs-lookup"><span data-stu-id="f0064-162">-Overwrite</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0064-163">注释</span><span class="sxs-lookup"><span data-stu-id="f0064-163">Remarks</span></span>  
 <span data-ttu-id="f0064-164">参数名称不区分大小写，并且可以为缩写形式。</span><span class="sxs-lookup"><span data-stu-id="f0064-164">Parameter names are not case sensitive and may be abbreviated.</span></span> <span data-ttu-id="f0064-165">参数值是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="f0064-165">Parameter values are case sensitive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0064-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0064-166">See Also</span></span>  
 [<span data-ttu-id="f0064-167">如何使用发布向导的 BizTalk Web 服务发布作为 Web 服务业务流程</span><span class="sxs-lookup"><span data-stu-id="f0064-167">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)