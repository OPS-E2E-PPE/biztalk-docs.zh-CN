---
title: 找到无效的证书 |Microsoft 文档
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
ms.openlocfilehash: 8fdf1d80818dd8e7dba349ea1dec9b69fa66a2fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257845"
---
# <a name="invalid-certificate-found"></a><span data-ttu-id="5264a-102">找到的证书无效</span><span class="sxs-lookup"><span data-stu-id="5264a-102">Invalid certificate found</span></span>
## <a name="details"></a><span data-ttu-id="5264a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5264a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5264a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5264a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5264a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5264a-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5264a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5264a-106">Event ID</span></span>|<span data-ttu-id="5264a-107">0</span><span class="sxs-lookup"><span data-stu-id="5264a-107">0</span></span>|  
|<span data-ttu-id="5264a-108">事件源</span><span class="sxs-lookup"><span data-stu-id="5264a-108">Event Source</span></span>|<span data-ttu-id="5264a-109">0</span><span class="sxs-lookup"><span data-stu-id="5264a-109">0</span></span>|  
|<span data-ttu-id="5264a-110">组件</span><span class="sxs-lookup"><span data-stu-id="5264a-110">Component</span></span>|<span data-ttu-id="5264a-111">0</span><span class="sxs-lookup"><span data-stu-id="5264a-111">0</span></span>|  
|<span data-ttu-id="5264a-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="5264a-112">Symbolic Name</span></span>|<span data-ttu-id="5264a-113">0</span><span class="sxs-lookup"><span data-stu-id="5264a-113">0</span></span>|  
|<span data-ttu-id="5264a-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="5264a-114">Message Text</span></span>|<span data-ttu-id="5264a-115">找到的证书无效</span><span class="sxs-lookup"><span data-stu-id="5264a-115">Invalid certificate found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5264a-116">解释</span><span class="sxs-lookup"><span data-stu-id="5264a-116">Explanation</span></span>  
 <span data-ttu-id="5264a-117">您为 WCF 传输提供的证书无效。</span><span class="sxs-lookup"><span data-stu-id="5264a-117">You did not provide a valid certificate for a WCF transport.</span></span>  

#### <a name="user-action"></a><span data-ttu-id="5264a-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="5264a-118">User Action</span></span>
<span data-ttu-id="5264a-119">添加证书。</span><span class="sxs-lookup"><span data-stu-id="5264a-119">Add a certificate.</span></span> 
  
## <a name="add-a-certificate"></a><span data-ttu-id="5264a-120">添加证书</span><span class="sxs-lookup"><span data-stu-id="5264a-120">Add a certificate</span></span>  
  
1.  <span data-ttu-id="5264a-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5264a-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5264a-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5264a-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="5264a-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="5264a-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="5264a-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="5264a-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="5264a-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="5264a-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="5264a-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="5264a-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="5264a-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5264a-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="5264a-128">在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5264a-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="5264a-129">单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="5264a-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="5264a-130">在**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分正确配置，以指示的有效证书。</span><span class="sxs-lookup"><span data-stu-id="5264a-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate valid certificates.</span></span>  
  
 <span data-ttu-id="5264a-131">对于 WCF 自定义和 WCF CustomIsolated 适配器，请确保中的搜索条件**证书引用**部分正确配置，以指示该证书中的有效证书**存储名称**.</span><span class="sxs-lookup"><span data-stu-id="5264a-131">For the WCF-Custom and the WCF-CustomIsolated adapters, ensure that the search criteria in the **Certificate Reference** section is configured properly to indicate a valid certificate in the certificate **Store name**.</span></span>  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a><span data-ttu-id="5264a-132">为标准 WCF 适配器添加证书</span><span class="sxs-lookup"><span data-stu-id="5264a-132">Add a certificate for standard WCF adapters</span></span>  
  
1.  <span data-ttu-id="5264a-133">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5264a-133">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5264a-134">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5264a-134">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="5264a-135">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="5264a-135">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="5264a-136">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="5264a-136">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="5264a-137">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="5264a-137">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="5264a-138">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="5264a-138">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="5264a-139">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5264a-139">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="5264a-140">在**WCF [***传输类型***] 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5264a-140">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="5264a-141">确保**指纹**为服务和客户端证书的属性指示证书中的有效证书**存储名称**。</span><span class="sxs-lookup"><span data-stu-id="5264a-141">Ensure that the **Thumbprint** properties for the service and client certificates indicate valid certificates in the certificate **Store name**.</span></span>  
  
 <span data-ttu-id="5264a-142">在“证书”管理单元中，确保为 WCF 传输安装有效的证书。</span><span class="sxs-lookup"><span data-stu-id="5264a-142">In the Certificate snap-in, make sure that valid certificates are installed for the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5264a-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5264a-143">See also</span></span> 
  
[<span data-ttu-id="5264a-144">将证书安装适用于这些 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="5264a-144">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  