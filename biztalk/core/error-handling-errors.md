---
title: "处理错误的错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 602be8a5-1f28-457d-8e12-ba06cff65491
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dafc64afb24ce8bb7995e7852a778b17a556f018
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-handling-errors"></a><span data-ttu-id="16f31-102">处理错误时出错</span><span class="sxs-lookup"><span data-stu-id="16f31-102">Error Handling Errors</span></span>
<span data-ttu-id="16f31-103">用于诊断和解决 WCF 错误处理错误的信息。</span><span class="sxs-lookup"><span data-stu-id="16f31-103">Information for diagnosing and resolving WCF Error Handling errors.</span></span>  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a><span data-ttu-id="16f31-104">错误处理选项“失败时禁用位置”和“失败时挂起请求消息”不应同时设置为 False</span><span class="sxs-lookup"><span data-stu-id="16f31-104">Error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false</span></span>    
||<span data-ttu-id="16f31-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="16f31-105">Details</span></span>|  
|-|-|  
|<span data-ttu-id="16f31-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="16f31-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="16f31-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="16f31-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="16f31-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="16f31-108">Event ID</span></span>|<span data-ttu-id="16f31-109">0</span><span class="sxs-lookup"><span data-stu-id="16f31-109">0</span></span>|  
|<span data-ttu-id="16f31-110">事件源</span><span class="sxs-lookup"><span data-stu-id="16f31-110">Event Source</span></span>|<span data-ttu-id="16f31-111">0</span><span class="sxs-lookup"><span data-stu-id="16f31-111">0</span></span>|  
|<span data-ttu-id="16f31-112">组件</span><span class="sxs-lookup"><span data-stu-id="16f31-112">Component</span></span>|<span data-ttu-id="16f31-113">0</span><span class="sxs-lookup"><span data-stu-id="16f31-113">0</span></span>|  
|<span data-ttu-id="16f31-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="16f31-114">Symbolic Name</span></span>|<span data-ttu-id="16f31-115">0</span><span class="sxs-lookup"><span data-stu-id="16f31-115">0</span></span>|  
|<span data-ttu-id="16f31-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="16f31-116">Message Text</span></span>|<span data-ttu-id="16f31-117">错误处理选项“失败时禁用位置”和“失败时挂起请求消息”不应都设置为 False，因为可能发生消息丢失。</span><span class="sxs-lookup"><span data-stu-id="16f31-117">The error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="16f31-118">请将一个或两个选项设置为 True。</span><span class="sxs-lookup"><span data-stu-id="16f31-118">Please set one or both options to true</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="16f31-119">解释</span><span class="sxs-lookup"><span data-stu-id="16f31-119">Explanation</span></span>  
 <span data-ttu-id="16f31-120">在 WCF NetMsmq 适配器选项中**禁用失败的位置**和**失败的挂起请求消息**不能二者都应该处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="16f31-120">In the WCF-NetMsmq adapter, the options **Disable location on failure** and **Suspend request message on failure** should not both be selected.</span></span> <span data-ttu-id="16f31-121">由于接收位置继续接收无效消息，但这些消息未被挂起并存储在 MessageBox 中，则可能发生消息丢失。</span><span class="sxs-lookup"><span data-stu-id="16f31-121">Message loss may occur as the receive location continues to receive invalid messages, while these messages are not suspended and stored in the Message Box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16f31-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="16f31-122">User Action</span></span>  
 <span data-ttu-id="16f31-123">使用以下过程配置适配器设置。</span><span class="sxs-lookup"><span data-stu-id="16f31-123">Use the following procedure to configure adapter settings.</span></span>    

1. <span data-ttu-id="16f31-124">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="16f31-124">Open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="16f31-125">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="16f31-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="16f31-126">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="16f31-126">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="16f31-127">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="16f31-127">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="16f31-128">选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="16f31-128">Select **Properties**.</span></span>  
  
6.  <span data-ttu-id="16f31-129">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="16f31-129">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="16f31-130">选择 **“配置”**。</span><span class="sxs-lookup"><span data-stu-id="16f31-130">Select **Configure**.</span></span>  
  
8.  <span data-ttu-id="16f31-131">在**WCF [***传输类型***] 传输属性**对话框中，选择**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="16f31-131">In the **WCF [***transport type***] Transport Properties** dialog box, select the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="16f31-132">在**错误处理**部分中，确保或者**禁用失败的位置**或**失败的挂起请求消息**已选中。</span><span class="sxs-lookup"><span data-stu-id="16f31-132">In the **Error Handling** section, ensure either **Disable location on failure** or **Suspend request message on failure** is checked.</span></span>