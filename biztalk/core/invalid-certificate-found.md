---
title: 找到的证书无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b3a9ae8-a9d7-4025-bacd-443e136ff980
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a069ee0c934f9a7636646a07bd5a7f777d88c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020581"
---
# <a name="invalid-certificate-found"></a><span data-ttu-id="cca7c-102">找到的证书无效</span><span class="sxs-lookup"><span data-stu-id="cca7c-102">Invalid certificate found</span></span>
## <a name="details"></a><span data-ttu-id="cca7c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cca7c-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="cca7c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cca7c-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="cca7c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="cca7c-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="cca7c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cca7c-106">Event ID</span></span>     |                                         <span data-ttu-id="cca7c-107">0</span><span class="sxs-lookup"><span data-stu-id="cca7c-107">0</span></span>                                          |
|  <span data-ttu-id="cca7c-108">事件源</span><span class="sxs-lookup"><span data-stu-id="cca7c-108">Event Source</span></span>   |                                         <span data-ttu-id="cca7c-109">0</span><span class="sxs-lookup"><span data-stu-id="cca7c-109">0</span></span>                                          |
|    <span data-ttu-id="cca7c-110">组件</span><span class="sxs-lookup"><span data-stu-id="cca7c-110">Component</span></span>    |                                         <span data-ttu-id="cca7c-111">0</span><span class="sxs-lookup"><span data-stu-id="cca7c-111">0</span></span>                                          |
|  <span data-ttu-id="cca7c-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="cca7c-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="cca7c-113">0</span><span class="sxs-lookup"><span data-stu-id="cca7c-113">0</span></span>                                          |
|  <span data-ttu-id="cca7c-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="cca7c-114">Message Text</span></span>   |                             <span data-ttu-id="cca7c-115">找到的证书无效</span><span class="sxs-lookup"><span data-stu-id="cca7c-115">Invalid certificate found</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="cca7c-116">解释</span><span class="sxs-lookup"><span data-stu-id="cca7c-116">Explanation</span></span>  
 <span data-ttu-id="cca7c-117">您为 WCF 传输提供的证书无效。</span><span class="sxs-lookup"><span data-stu-id="cca7c-117">You did not provide a valid certificate for a WCF transport.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="cca7c-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="cca7c-118">User Action</span></span>
<span data-ttu-id="cca7c-119">添加证书。</span><span class="sxs-lookup"><span data-stu-id="cca7c-119">Add a certificate.</span></span> 
  
## <a name="add-a-certificate"></a><span data-ttu-id="cca7c-120">添加证书</span><span class="sxs-lookup"><span data-stu-id="cca7c-120">Add a certificate</span></span>  
  
1. <span data-ttu-id="cca7c-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cca7c-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="cca7c-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="cca7c-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="cca7c-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="cca7c-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="cca7c-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="cca7c-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="cca7c-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="cca7c-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="cca7c-128">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="cca7c-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="cca7c-129">单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="cca7c-130">在中**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分已正确配置，以显示有效证书。</span><span class="sxs-lookup"><span data-stu-id="cca7c-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
    <span data-ttu-id="cca7c-131">对于 Wcf-custom 和 Wcf-customisolated 适配器，请确保中的搜索条件**证书引用**部分已正确配置，以指示该证书中的有效证书**存储区名称**.</span><span class="sxs-lookup"><span data-stu-id="cca7c-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a><span data-ttu-id="cca7c-132">为标准 WCF 适配器添加证书</span><span class="sxs-lookup"><span data-stu-id="cca7c-132">Add a certificate for standard WCF adapters</span></span>  
  
1. <span data-ttu-id="cca7c-133">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cca7c-134">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="cca7c-135">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="cca7c-135">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="cca7c-136">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="cca7c-136">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="cca7c-137">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-137">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="cca7c-138">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="cca7c-138">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="cca7c-139">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-139">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="cca7c-140">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="cca7c-140">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="cca7c-141">絋粄**指纹**服务和客户端证书的属性显示在证书中的有效证书**存储区名称**。</span><span class="sxs-lookup"><span data-stu-id="cca7c-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in the certificate **Store name**.</span></span>  
  
   <span data-ttu-id="cca7c-142">在“证书”管理单元中，确保为 WCF 传输安装有效的证书。</span><span class="sxs-lookup"><span data-stu-id="cca7c-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca7c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cca7c-143">See also</span></span> 
  
[<span data-ttu-id="cca7c-144">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="cca7c-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  