---
title: 证书引用不明确 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a6a60d-97e6-4c60-86be-83efb4a50f99
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ac43f85b590ede746bbd14065d8e01701d1e91f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988830"
---
# <a name="ambiguous-certificate-reference"></a><span data-ttu-id="af3a7-102">证书引用不明确</span><span class="sxs-lookup"><span data-stu-id="af3a7-102">Ambiguous certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="af3a7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="af3a7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="af3a7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="af3a7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="af3a7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="af3a7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="af3a7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="af3a7-106">Event ID</span></span>     |                                         <span data-ttu-id="af3a7-107">0</span><span class="sxs-lookup"><span data-stu-id="af3a7-107">0</span></span>                                          |
|  <span data-ttu-id="af3a7-108">事件源</span><span class="sxs-lookup"><span data-stu-id="af3a7-108">Event Source</span></span>   |                                         <span data-ttu-id="af3a7-109">0</span><span class="sxs-lookup"><span data-stu-id="af3a7-109">0</span></span>                                          |
|    <span data-ttu-id="af3a7-110">组件</span><span class="sxs-lookup"><span data-stu-id="af3a7-110">Component</span></span>    |                                         <span data-ttu-id="af3a7-111">0</span><span class="sxs-lookup"><span data-stu-id="af3a7-111">0</span></span>                                          |
|  <span data-ttu-id="af3a7-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="af3a7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="af3a7-113">0</span><span class="sxs-lookup"><span data-stu-id="af3a7-113">0</span></span>                                          |
|  <span data-ttu-id="af3a7-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="af3a7-114">Message Text</span></span>   |       <span data-ttu-id="af3a7-115">证书引用不明确，找到了多个有效证书</span><span class="sxs-lookup"><span data-stu-id="af3a7-115">Ambiguous certificate reference; more than one valid certificate found</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="af3a7-116">解释</span><span class="sxs-lookup"><span data-stu-id="af3a7-116">Explanation</span></span>  
 <span data-ttu-id="af3a7-117">找到了多个有效证书。</span><span class="sxs-lookup"><span data-stu-id="af3a7-117">More than one valid certificate was found.</span></span>  
  
#### <a name="user-action"></a><span data-ttu-id="af3a7-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="af3a7-118">User action</span></span>  
 <span data-ttu-id="af3a7-119">验证只有一个配置有效的证书。</span><span class="sxs-lookup"><span data-stu-id="af3a7-119">Verify only one valid certificate is configured.</span></span>  
  
## <a name="verify-certificate"></a><span data-ttu-id="af3a7-120">验证证书</span><span class="sxs-lookup"><span data-stu-id="af3a7-120">Verify certificate</span></span> 
  
1. <span data-ttu-id="af3a7-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="af3a7-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="af3a7-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="af3a7-123">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="af3a7-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="af3a7-124">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="af3a7-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-125">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="af3a7-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="af3a7-126">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="af3a7-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-127">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="af3a7-128">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="af3a7-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="af3a7-129">单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="af3a7-130">在中**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分已正确配置，以指示证书中的只有一个证书**应用商店名称**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a><span data-ttu-id="af3a7-131">对于 Wcf-custom 和 Wcf-customisolated 适配器验证证书</span><span class="sxs-lookup"><span data-stu-id="af3a7-131">Verify a certificate for the WCF-Custom and the WCF-CustomIsolated adapters</span></span>  
  
1. <span data-ttu-id="af3a7-132">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="af3a7-132">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2. <span data-ttu-id="af3a7-133">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-133">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3. <span data-ttu-id="af3a7-134">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="af3a7-134">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="af3a7-135">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="af3a7-135">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="af3a7-136">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-136">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="af3a7-137">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="af3a7-137">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="af3a7-138">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-138">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="af3a7-139">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**行为**选项卡。</span><span class="sxs-lookup"><span data-stu-id="af3a7-139">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="af3a7-140">确保中的搜索条件**证书引用**部分已正确配置，以指示证书中的只有一个证书**存储区名称**。</span><span class="sxs-lookup"><span data-stu-id="af3a7-140">Ensure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
10. <span data-ttu-id="af3a7-141">在“证书”管理单元中，确保只为您配置为 WCF 传输的搜索条件安装了一个证书。</span><span class="sxs-lookup"><span data-stu-id="af3a7-141">In the Certificate snap-in, make sure only one certificate is installed for the search criteria you configured to the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3a7-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af3a7-142">See also</span></span>
[<span data-ttu-id="af3a7-143">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="af3a7-143">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
 