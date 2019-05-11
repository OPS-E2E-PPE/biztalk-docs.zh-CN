---
title: 如何启用 ASP.NET 4.0 的已发布的 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58646ff2-77a3-49dc-8593-f6e41d85d4f3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5613e22070b4103eb3744ebb8b7a0d008ca6df1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337969"
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a><span data-ttu-id="04ced-102">如何为已发布的 Web Services 启用 ASP.NET 4.0</span><span class="sxs-lookup"><span data-stu-id="04ced-102">How to Enable ASP.NET 4.0 for Published Web Services</span></span>
<span data-ttu-id="04ced-103">在 IIS 中设置的 ASP.Net 版本。</span><span class="sxs-lookup"><span data-stu-id="04ced-103">Set the ASP.Net version in IIS.</span></span>

<span data-ttu-id="04ced-104">BizTalk Server Web Services 发布向导依赖于提供 ASP.NET，这是.NET Framework 附带的功能。</span><span class="sxs-lookup"><span data-stu-id="04ced-104">The BizTalk Server Web Services Publishing Wizard relies on functionality provided with ASP.NET, which is included with the .NET Framework.</span></span> <span data-ttu-id="04ced-105">包含您选择的.NET CLR 版本的 ASP.Net 版本。</span><span class="sxs-lookup"><span data-stu-id="04ced-105">The ASP.Net versions are included with the .NET CLR version you choose.</span></span> 

<span data-ttu-id="04ced-106">本主题演示如何更改.NET CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="04ced-106">This topic shows you how to change the .NET CLR version.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="04ced-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="04ced-107">Prerequisites</span></span>

<span data-ttu-id="04ced-108">IIS 是附带**Web 服务器 (IIS)** 在操作系统中的角色。</span><span class="sxs-lookup"><span data-stu-id="04ced-108">IIS is included with the **Web Server (IIS)** role in the operating system.</span></span> <span data-ttu-id="04ced-109">在安装此角色时，还可以选择较新版本的 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="04ced-109">When you install this role, also select the newer version of ASP.NET.</span></span> 
  
## <a name="update-an-application-pool"></a><span data-ttu-id="04ced-110">更新应用程序池</span><span class="sxs-lookup"><span data-stu-id="04ced-110">Update an application pool</span></span>
  
1.  <span data-ttu-id="04ced-111">打开**Internet Information Services (IIS) 管理器**:</span><span class="sxs-lookup"><span data-stu-id="04ced-111">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="04ced-112">在中**服务器管理器**，选择**工具**。</span><span class="sxs-lookup"><span data-stu-id="04ced-112">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="04ced-113">选择**Internet Information Services (IIS) 管理器**。</span><span class="sxs-lookup"><span data-stu-id="04ced-113">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="04ced-114">展开服务器名称，然后选择**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="04ced-114">Expand the server name, and select **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="04ced-115">选择应用程序池，并打开**基本设置**。</span><span class="sxs-lookup"><span data-stu-id="04ced-115">Select the app pool, and open the **Basic Settings**.</span></span>  
  
4. <span data-ttu-id="04ced-116">设置 **.NET CLR 版本**为较新版本，然后选择**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="04ced-116">Set the **.NET CLR version** to the newer version, and select **OK** to save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="04ced-117">此外可以更改 web.config 文件中的版本。</span><span class="sxs-lookup"><span data-stu-id="04ced-117">You can also change the version in the web.config file.</span></span>
 
## <a name="allow-the-aspnet-extension"></a><span data-ttu-id="04ced-118">允许使用 ASP.Net 扩展插件</span><span class="sxs-lookup"><span data-stu-id="04ced-118">Allow the ASP.Net extension</span></span>
  
1.  <span data-ttu-id="04ced-119">打开**Internet Information Services (IIS) 管理器**:</span><span class="sxs-lookup"><span data-stu-id="04ced-119">Open **Internet Information Services (IIS) Manager**:</span></span>

    1. <span data-ttu-id="04ced-120">在中**服务器管理器**，选择**工具**。</span><span class="sxs-lookup"><span data-stu-id="04ced-120">In **Server Manager**, select **Tools**.</span></span>
    2. <span data-ttu-id="04ced-121">选择**Internet Information Services (IIS) 管理器**。</span><span class="sxs-lookup"><span data-stu-id="04ced-121">Select **Internet Information Services (IIS) Manager**.</span></span>
  
2.  <span data-ttu-id="04ced-122">选择服务器名称，然后双击**ISAPI 和 CGI 限制**。</span><span class="sxs-lookup"><span data-stu-id="04ced-122">Select the server name, and double-click **ISAPI and CGI Restrictions**.</span></span>  
  
3. <span data-ttu-id="04ced-123">确认 ASP.NET 是否**允许**的 32 位和 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="04ced-123">Confirm ASP.NET is **Allowed** for the 32-bit and 64-bit versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ced-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="04ced-124">See Also</span></span>  
 [<span data-ttu-id="04ced-125">规划发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="04ced-125">Planning for Publishing Web Services</span></span>](../core/planning-for-publishing-web-services2.md)