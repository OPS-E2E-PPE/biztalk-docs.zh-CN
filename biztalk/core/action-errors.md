---
title: 操作错误 |Microsoft Docs
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
ms.openlocfilehash: c3cb63e90f85c830c30524b3adc1e3b0d86ab8b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997270"
---
# <a name="action-errors"></a><span data-ttu-id="ba159-102">操作错误</span><span class="sxs-lookup"><span data-stu-id="ba159-102">Action Errors</span></span>
<span data-ttu-id="ba159-103">本部分包含有关诊断和解决 WCF 操作错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ba159-103">This section contains detailed information for diagnosing and resolving WCF Action errors.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ba159-104">详细信息</span><span class="sxs-lookup"><span data-stu-id="ba159-104">Details</span></span>  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ba159-105">产品名称</span><span class="sxs-lookup"><span data-stu-id="ba159-105">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| <span data-ttu-id="ba159-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ba159-106">Product Version</span></span> |                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                              |
|    <span data-ttu-id="ba159-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ba159-107">Event ID</span></span>     |                                                                          <span data-ttu-id="ba159-108">0</span><span class="sxs-lookup"><span data-stu-id="ba159-108">0</span></span>                                                                          |
|  <span data-ttu-id="ba159-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ba159-109">Event Source</span></span>   |                                                                          <span data-ttu-id="ba159-110">0</span><span class="sxs-lookup"><span data-stu-id="ba159-110">0</span></span>                                                                          |
|    <span data-ttu-id="ba159-111">组件</span><span class="sxs-lookup"><span data-stu-id="ba159-111">Component</span></span>    |                                                                          <span data-ttu-id="ba159-112">0</span><span class="sxs-lookup"><span data-stu-id="ba159-112">0</span></span>                                                                          |
|  <span data-ttu-id="ba159-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ba159-113">Symbolic Name</span></span>  |                                                                          <span data-ttu-id="ba159-114">0</span><span class="sxs-lookup"><span data-stu-id="ba159-114">0</span></span>                                                                          |
|  <span data-ttu-id="ba159-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ba159-115">Message Text</span></span>   | <span data-ttu-id="ba159-116">单个操作不能包含换行符。</span><span class="sxs-lookup"><span data-stu-id="ba159-116">A single action cannot contain new line characters.</span></span> <span data-ttu-id="ba159-117">删除所有换行符。</span><span class="sxs-lookup"><span data-stu-id="ba159-117">Remove all new line characters.</span></span> <span data-ttu-id="ba159-118">或者，若要指定多个操作，请使用操作映射语法。</span><span class="sxs-lookup"><span data-stu-id="ba159-118">Or, to specify multiple actions, use the action mapping syntax.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ba159-119">解释</span><span class="sxs-lookup"><span data-stu-id="ba159-119">Explanation</span></span>  
 <span data-ttu-id="ba159-120">此错误表示发送端口的操作属性包含换行符，这是不允许的。</span><span class="sxs-lookup"><span data-stu-id="ba159-120">This error indicates the action property of a send port contains a new line character, which is not allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba159-121">当操作定义为映射时，不存在此限制。</span><span class="sxs-lookup"><span data-stu-id="ba159-121">This restriction does not apply when the action is defined as a mapping.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ba159-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="ba159-122">User Action</span></span>  
 <span data-ttu-id="ba159-123">使用以下过程来修复操作属性。</span><span class="sxs-lookup"><span data-stu-id="ba159-123">Use the following procedure to fix the action property.</span></span>  
  
 
1. <span data-ttu-id="ba159-124">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="ba159-124">Open **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="ba159-125">在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="ba159-125">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="ba159-126">找到您的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="ba159-126">Locate your application, and then locate your transport.</span></span>  
  
4. <span data-ttu-id="ba159-127">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="ba159-127">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="ba159-128">选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ba159-128">Select **Properties**.</span></span>  
  
6. <span data-ttu-id="ba159-129">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="ba159-129">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="ba159-130">选择 **“配置”**。</span><span class="sxs-lookup"><span data-stu-id="ba159-130">Select **Configure**.</span></span>  
  
8. <span data-ttu-id="ba159-131">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，选择**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ba159-131">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, select the **General** tab.</span></span>  
  
9. <span data-ttu-id="ba159-132">在中**SOAP 操作标头**部分中，删除中的新行字符**操作**文本框。</span><span class="sxs-lookup"><span data-stu-id="ba159-132">In the **SOAP Action header** section, remove the new line character from the **Action** text box.</span></span>  

## <a name="more-good-info"></a><span data-ttu-id="ba159-133">更多有用信息</span><span class="sxs-lookup"><span data-stu-id="ba159-133">More good info</span></span>  
 <span data-ttu-id="ba159-134">有关操作的其他信息，请参阅[对于 WCF 发送适配器指定 SOAP 操作](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span><span class="sxs-lookup"><span data-stu-id="ba159-134">For additional information on actions, see [Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md)</span></span>