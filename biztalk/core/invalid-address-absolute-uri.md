---
title: "无效的地址 (绝对 uri) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db292ad-9105-492d-a6c5-a7108159901a
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af2cb19c793bdcd7ab4a1dc18eb0ea1c98a991ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-absolute-uri"></a><span data-ttu-id="a3d24-102">地址无效（绝对 URI）</span><span class="sxs-lookup"><span data-stu-id="a3d24-102">Invalid address (absolute uri)</span></span>
## <a name="details"></a><span data-ttu-id="a3d24-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a3d24-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3d24-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a3d24-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a3d24-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a3d24-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="a3d24-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a3d24-106">Event ID</span></span>|<span data-ttu-id="a3d24-107">0</span><span class="sxs-lookup"><span data-stu-id="a3d24-107">0</span></span>|  
|<span data-ttu-id="a3d24-108">事件源</span><span class="sxs-lookup"><span data-stu-id="a3d24-108">Event Source</span></span>|<span data-ttu-id="a3d24-109">0</span><span class="sxs-lookup"><span data-stu-id="a3d24-109">0</span></span>|  
|<span data-ttu-id="a3d24-110">组件</span><span class="sxs-lookup"><span data-stu-id="a3d24-110">Component</span></span>|<span data-ttu-id="a3d24-111">0</span><span class="sxs-lookup"><span data-stu-id="a3d24-111">0</span></span>|  
|<span data-ttu-id="a3d24-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="a3d24-112">Symbolic Name</span></span>|<span data-ttu-id="a3d24-113">0</span><span class="sxs-lookup"><span data-stu-id="a3d24-113">0</span></span>|  
|<span data-ttu-id="a3d24-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="a3d24-114">Message Text</span></span>|<span data-ttu-id="a3d24-115">地址无效；“{0}”不是格式正确的绝对 URI</span><span class="sxs-lookup"><span data-stu-id="a3d24-115">Invalid address; "{0}" is not a well-formed absolute uri</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3d24-116">解释</span><span class="sxs-lookup"><span data-stu-id="a3d24-116">Explanation</span></span>  
 <span data-ttu-id="a3d24-117">此错误事件表明您未提供具有正确格式的绝对地址的进程内 WCF 传输。</span><span class="sxs-lookup"><span data-stu-id="a3d24-117">This error event indicates that you did not provide an in-process WCF transport with a well-formed absolute address.</span></span> <span data-ttu-id="a3d24-118">例如，您无法将进程内 WCF 传输的“地址”属性设置为相对地址（例如 /path/service.svc）。</span><span class="sxs-lookup"><span data-stu-id="a3d24-118">For example, you cannot set the Address property of the in-process WCF transport to a relative address, such as /path/service.svc.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3d24-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="a3d24-119">User Action</span></span>  
 <span data-ttu-id="a3d24-120">将进程内 WCF 传输的地址更改为格式正确的绝对地址。</span><span class="sxs-lookup"><span data-stu-id="a3d24-120">Change the address of the in-process WCF transport to a well-formed absolute address.</span></span>  
  
1.  <span data-ttu-id="a3d24-121">单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a3d24-121">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a3d24-122">在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a3d24-122">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="a3d24-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="a3d24-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="a3d24-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="a3d24-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="a3d24-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="a3d24-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="a3d24-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="a3d24-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="a3d24-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a3d24-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="a3d24-128">在**WCF [***传输类型***] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a3d24-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="a3d24-129">在**地址 (URI)**文本框。</span><span class="sxs-lookup"><span data-stu-id="a3d24-129">In the **Address (URI)** text box.</span></span> <span data-ttu-id="a3d24-130">更改的地址。</span><span class="sxs-lookup"><span data-stu-id="a3d24-130">change the address.</span></span> <span data-ttu-id="a3d24-131">例如，格式正确的绝对地址为 http://localhost/path/service.svc</span><span class="sxs-lookup"><span data-stu-id="a3d24-131">An example of a well-formed absolute address is http://localhost/path/service.svc</span></span>