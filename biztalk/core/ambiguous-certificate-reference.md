---
title: 不明确的证书引用 |Microsoft 文档
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
ms.openlocfilehash: 304ded9572ba6598f7f2132a678a14b2b3301c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230701"
---
# <a name="ambiguous-certificate-reference"></a><span data-ttu-id="7fb73-102">证书引用不明确</span><span class="sxs-lookup"><span data-stu-id="7fb73-102">Ambiguous certificate reference</span></span>
## <a name="details"></a><span data-ttu-id="7fb73-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7fb73-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7fb73-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7fb73-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7fb73-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7fb73-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="7fb73-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7fb73-106">Event ID</span></span>|<span data-ttu-id="7fb73-107">0</span><span class="sxs-lookup"><span data-stu-id="7fb73-107">0</span></span>|  
|<span data-ttu-id="7fb73-108">事件源</span><span class="sxs-lookup"><span data-stu-id="7fb73-108">Event Source</span></span>|<span data-ttu-id="7fb73-109">0</span><span class="sxs-lookup"><span data-stu-id="7fb73-109">0</span></span>|  
|<span data-ttu-id="7fb73-110">组件</span><span class="sxs-lookup"><span data-stu-id="7fb73-110">Component</span></span>|<span data-ttu-id="7fb73-111">0</span><span class="sxs-lookup"><span data-stu-id="7fb73-111">0</span></span>|  
|<span data-ttu-id="7fb73-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="7fb73-112">Symbolic Name</span></span>|<span data-ttu-id="7fb73-113">0</span><span class="sxs-lookup"><span data-stu-id="7fb73-113">0</span></span>|  
|<span data-ttu-id="7fb73-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="7fb73-114">Message Text</span></span>|<span data-ttu-id="7fb73-115">证书引用不明确，找到了多个有效证书</span><span class="sxs-lookup"><span data-stu-id="7fb73-115">Ambiguous certificate reference; more than one valid certificate found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7fb73-116">解释</span><span class="sxs-lookup"><span data-stu-id="7fb73-116">Explanation</span></span>  
 <span data-ttu-id="7fb73-117">找到了多个有效证书。</span><span class="sxs-lookup"><span data-stu-id="7fb73-117">More than one valid certificate was found.</span></span>  
  
#### <a name="user-action"></a><span data-ttu-id="7fb73-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="7fb73-118">User action</span></span>  
 <span data-ttu-id="7fb73-119">验证只有一个配置有效的证书。</span><span class="sxs-lookup"><span data-stu-id="7fb73-119">Verify only one valid certificate is configured.</span></span>  
  
## <a name="verify-certificate"></a><span data-ttu-id="7fb73-120">验证证书</span><span class="sxs-lookup"><span data-stu-id="7fb73-120">Verify certificate</span></span> 
  
1.  <span data-ttu-id="7fb73-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7fb73-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="7fb73-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="7fb73-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="7fb73-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="7fb73-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="7fb73-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="7fb73-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="7fb73-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="7fb73-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="7fb73-128">在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="7fb73-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="7fb73-129">单击 **“编辑”**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-129">Click **Edit**.</span></span>  
  
10. <span data-ttu-id="7fb73-130">在**标识编辑器**对话框框中，请确保中的搜索条件**证书引用**部分正确配置，以指示证书中的只有一个证书**应用商店名称**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-130">In the **Identity Editor** dialog box, make sure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
## <a name="verify-a-certificate-for-the-wcf-custom-and-the-wcf-customisolated-adapters"></a><span data-ttu-id="7fb73-131">为 WCF 自定义和 WCF CustomIsolated 适配器验证证书</span><span class="sxs-lookup"><span data-stu-id="7fb73-131">Verify a certificate for the WCF-Custom and the WCF-CustomIsolated adapters</span></span>  
  
1.  <span data-ttu-id="7fb73-132">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7fb73-132">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="7fb73-133">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-133">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="7fb73-134">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="7fb73-134">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="7fb73-135">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="7fb73-135">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="7fb73-136">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-136">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="7fb73-137">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="7fb73-137">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="7fb73-138">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-138">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="7fb73-139">在**WCF [***传输类型***] 传输属性**对话框中，单击**行为**选项卡。</span><span class="sxs-lookup"><span data-stu-id="7fb73-139">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  
  
9. <span data-ttu-id="7fb73-140">确保中的搜索条件**证书引用**部分正确配置，以指示证书中的只有一个证书**存储名称**。</span><span class="sxs-lookup"><span data-stu-id="7fb73-140">Ensure the search criteria in the **Certificate Reference** section is configured properly to indicate only one certificate in the certificate **Store name**.</span></span>  
  
10. <span data-ttu-id="7fb73-141">在“证书”管理单元中，确保只为您配置为 WCF 传输的搜索条件安装了一个证书。</span><span class="sxs-lookup"><span data-stu-id="7fb73-141">In the Certificate snap-in, make sure only one certificate is installed for the search criteria you configured to the WCF transport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb73-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fb73-142">See also</span></span>
[<span data-ttu-id="7fb73-143">将证书安装适用于这些 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="7fb73-143">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
 