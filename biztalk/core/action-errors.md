---
title: 操作错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87cf0a5b-d1dd-4807-9660-e8a8b7012b40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f25f1f15307077943ef370a335885690bea22c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225589"
---
# <a name="action-errors"></a><span data-ttu-id="0f973-102">操作错误</span><span class="sxs-lookup"><span data-stu-id="0f973-102">Action Errors</span></span>
<span data-ttu-id="0f973-103">本部分包含有关诊断和解决 WCF 操作错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0f973-103">This section contains detailed information for diagnosing and resolving WCF Action errors.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0f973-104">详细信息</span><span class="sxs-lookup"><span data-stu-id="0f973-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f973-105">产品名称</span><span class="sxs-lookup"><span data-stu-id="0f973-105">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0f973-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0f973-106">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="0f973-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0f973-107">Event ID</span></span>|<span data-ttu-id="0f973-108">0</span><span class="sxs-lookup"><span data-stu-id="0f973-108">0</span></span>|  
|<span data-ttu-id="0f973-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0f973-109">Event Source</span></span>|<span data-ttu-id="0f973-110">0</span><span class="sxs-lookup"><span data-stu-id="0f973-110">0</span></span>|  
|<span data-ttu-id="0f973-111">组件</span><span class="sxs-lookup"><span data-stu-id="0f973-111">Component</span></span>|<span data-ttu-id="0f973-112">0</span><span class="sxs-lookup"><span data-stu-id="0f973-112">0</span></span>|  
|<span data-ttu-id="0f973-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0f973-113">Symbolic Name</span></span>|<span data-ttu-id="0f973-114">0</span><span class="sxs-lookup"><span data-stu-id="0f973-114">0</span></span>|  
|<span data-ttu-id="0f973-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0f973-115">Message Text</span></span>|<span data-ttu-id="0f973-116">单个操作不能包含换行符。</span><span class="sxs-lookup"><span data-stu-id="0f973-116">A single action cannot contain new line characters.</span></span> <span data-ttu-id="0f973-117">删除所有换行符。</span><span class="sxs-lookup"><span data-stu-id="0f973-117">Remove all new line characters.</span></span> <span data-ttu-id="0f973-118">或者，若要指定多个操作，请使用操作映射语法。</span><span class="sxs-lookup"><span data-stu-id="0f973-118">Or, to specify multiple actions, use the action mapping syntax.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0f973-119">解释</span><span class="sxs-lookup"><span data-stu-id="0f973-119">Explanation</span></span>  
 <span data-ttu-id="0f973-120">此错误表示发送端口的操作属性包含换行符，这是不允许的。</span><span class="sxs-lookup"><span data-stu-id="0f973-120">This error indicates the action property of a send port contains a new line character, which is not allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f973-121">当操作定义为映射时，不存在此限制。</span><span class="sxs-lookup"><span data-stu-id="0f973-121">This restriction does not apply when the action is defined as a mapping.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f973-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="0f973-122">User Action</span></span>  
 <span data-ttu-id="0f973-123">使用以下过程来修复操作属性。</span><span class="sxs-lookup"><span data-stu-id="0f973-123">Use the following procedure to fix the action property.</span></span>  
  
 
1.  <span data-ttu-id="0f973-124">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="0f973-124">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0f973-125">在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0f973-125">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="0f973-126">找到您的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="0f973-126">Locate your application, and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="0f973-127">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="0f973-127">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="0f973-128">选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="0f973-128">Select **Properties**.</span></span>  
  
6.  <span data-ttu-id="0f973-129">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="0f973-129">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="0f973-130">选择 **“配置”**。</span><span class="sxs-lookup"><span data-stu-id="0f973-130">Select **Configure**.</span></span>  
  
8.  <span data-ttu-id="0f973-131">在**WCF [***传输类型***] 传输属性**对话框中，选择**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="0f973-131">In the **WCF [***transport type***] Transport Properties** dialog box, select the **General** tab.</span></span>  
  
9. <span data-ttu-id="0f973-132">在**SOAP 操作标头**部分中，删除中的新行字符**操作**文本框。</span><span class="sxs-lookup"><span data-stu-id="0f973-132">In the **SOAP Action header** section, remove the new line character from the **Action** text box.</span></span>  

## <a name="more-good-info"></a><span data-ttu-id="0f973-133">良好的详细信息</span><span class="sxs-lookup"><span data-stu-id="0f973-133">More good info</span></span>  
 <span data-ttu-id="0f973-134">有关操作的其他信息，请参阅[指定 WCF 发送适配器的 SOAP 操作](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span><span class="sxs-lookup"><span data-stu-id="0f973-134">For additional information on actions, see [Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span></span>