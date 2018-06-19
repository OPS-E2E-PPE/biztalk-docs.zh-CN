---
title: 找不到证书 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629b199f-1884-4e88-beaa-a2e5c5e792e9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1c18f112edc14375e6edc2aaa52c9e468d1bd39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232605"
---
# <a name="certificate-not-found"></a><span data-ttu-id="67a89-102">找不到证书</span><span class="sxs-lookup"><span data-stu-id="67a89-102">Certificate not found</span></span>
## <a name="details"></a><span data-ttu-id="67a89-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="67a89-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67a89-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="67a89-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="67a89-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="67a89-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="67a89-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="67a89-106">Event ID</span></span>|<span data-ttu-id="67a89-107">0</span><span class="sxs-lookup"><span data-stu-id="67a89-107">0</span></span>|  
|<span data-ttu-id="67a89-108">事件源</span><span class="sxs-lookup"><span data-stu-id="67a89-108">Event Source</span></span>|<span data-ttu-id="67a89-109">0</span><span class="sxs-lookup"><span data-stu-id="67a89-109">0</span></span>|  
|<span data-ttu-id="67a89-110">组件</span><span class="sxs-lookup"><span data-stu-id="67a89-110">Component</span></span>|<span data-ttu-id="67a89-111">0</span><span class="sxs-lookup"><span data-stu-id="67a89-111">0</span></span>|  
|<span data-ttu-id="67a89-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="67a89-112">Symbolic Name</span></span>|<span data-ttu-id="67a89-113">0</span><span class="sxs-lookup"><span data-stu-id="67a89-113">0</span></span>|  
|<span data-ttu-id="67a89-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="67a89-114">Message Text</span></span>|<span data-ttu-id="67a89-115">找不到证书。</span><span class="sxs-lookup"><span data-stu-id="67a89-115">Certificate not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67a89-116">解释</span><span class="sxs-lookup"><span data-stu-id="67a89-116">Explanation</span></span>  
 <span data-ttu-id="67a89-117">找不到给定的搜索条件的证书。</span><span class="sxs-lookup"><span data-stu-id="67a89-117">A certificate could not be found for the given search criteria.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="67a89-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="67a89-118">User Action</span></span>
<span data-ttu-id="67a89-119">验证证书的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="67a89-119">Verify search criteria for certificates.</span></span> 
  
## <a name="verify-search-criteria"></a><span data-ttu-id="67a89-120">验证搜索条件</span><span class="sxs-lookup"><span data-stu-id="67a89-120">Verify search criteria</span></span>  
  
1.  <span data-ttu-id="67a89-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="67a89-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="67a89-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="67a89-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="67a89-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="67a89-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="67a89-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="67a89-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="67a89-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="67a89-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="67a89-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="67a89-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="67a89-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="67a89-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="67a89-128">在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="67a89-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="67a89-129">单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="67a89-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="67a89-130">在**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分正确配置，以指示的有效证书。</span><span class="sxs-lookup"><span data-stu-id="67a89-130">In the **Identity Editor** dialog box, make sure that the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
 <span data-ttu-id="67a89-131">对于 WCF 自定义和 WCF CustomIsolated 适配器，请确保中的搜索条件**证书引用**部分正确配置，以指示该证书中的有效证书**存储名称**.</span><span class="sxs-lookup"><span data-stu-id="67a89-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-search-criteria-for-standard-wcf-adapters"></a><span data-ttu-id="67a89-132">验证标准 WCF 适配器的搜索条件</span><span class="sxs-lookup"><span data-stu-id="67a89-132">Verify search criteria for standard WCF adapters</span></span>  
  
1.  <span data-ttu-id="67a89-133">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="67a89-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="67a89-134">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="67a89-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="67a89-135">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="67a89-135">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="67a89-136">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="67a89-136">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="67a89-137">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="67a89-137">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="67a89-138">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="67a89-138">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="67a89-139">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="67a89-139">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="67a89-140">在**WCF [***传输类型***] 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="67a89-140">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="67a89-141">确保**指纹**为服务和客户端证书的属性指示在证书存储中的有效证书。</span><span class="sxs-lookup"><span data-stu-id="67a89-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in certificate stores.</span></span>  
  
10. <span data-ttu-id="67a89-142">在“证书”管理单元中，确保为 WCF 传输安装有效的证书。</span><span class="sxs-lookup"><span data-stu-id="67a89-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  

## <a name="see-also"></a><span data-ttu-id="67a89-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67a89-143">See also</span></span> 
  
-   [<span data-ttu-id="67a89-144">将证书安装适用于这些 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="67a89-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
