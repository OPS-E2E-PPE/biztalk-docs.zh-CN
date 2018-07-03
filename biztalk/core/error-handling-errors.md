---
title: 处理错误的错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 602be8a5-1f28-457d-8e12-ba06cff65491
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c494614465df4faeead9ec30d79dfdf47cc321c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999078"
---
# <a name="error-handling-errors"></a><span data-ttu-id="2a90b-102">处理错误时出错</span><span class="sxs-lookup"><span data-stu-id="2a90b-102">Error Handling Errors</span></span>
<span data-ttu-id="2a90b-103">有关诊断和解决 WCF 错误处理错误的信息。</span><span class="sxs-lookup"><span data-stu-id="2a90b-103">Information for diagnosing and resolving WCF Error Handling errors.</span></span>  

## <a name="error-handling-options-disable-location-on-failure-and-suspend-request-message-on-failure-should-not-both-be-set-to-false"></a><span data-ttu-id="2a90b-104">错误处理选项“失败时禁用位置”和“失败时挂起请求消息”不应同时设置为 False</span><span class="sxs-lookup"><span data-stu-id="2a90b-104">Error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false</span></span>    

|                 |                                                                                                <span data-ttu-id="2a90b-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a90b-105">Details</span></span>                                                                                                 |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2a90b-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="2a90b-106">Product Name</span></span>   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                           |
| <span data-ttu-id="2a90b-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="2a90b-107">Product Version</span></span> |                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                       |
|    <span data-ttu-id="2a90b-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2a90b-108">Event ID</span></span>     |                                                                                                   <span data-ttu-id="2a90b-109">0</span><span class="sxs-lookup"><span data-stu-id="2a90b-109">0</span></span>                                                                                                    |
|  <span data-ttu-id="2a90b-110">事件源</span><span class="sxs-lookup"><span data-stu-id="2a90b-110">Event Source</span></span>   |                                                                                                   <span data-ttu-id="2a90b-111">0</span><span class="sxs-lookup"><span data-stu-id="2a90b-111">0</span></span>                                                                                                    |
|    <span data-ttu-id="2a90b-112">组件</span><span class="sxs-lookup"><span data-stu-id="2a90b-112">Component</span></span>    |                                                                                                   <span data-ttu-id="2a90b-113">0</span><span class="sxs-lookup"><span data-stu-id="2a90b-113">0</span></span>                                                                                                    |
|  <span data-ttu-id="2a90b-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="2a90b-114">Symbolic Name</span></span>  |                                                                                                   <span data-ttu-id="2a90b-115">0</span><span class="sxs-lookup"><span data-stu-id="2a90b-115">0</span></span>                                                                                                    |
|  <span data-ttu-id="2a90b-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="2a90b-116">Message Text</span></span>   | <span data-ttu-id="2a90b-117">错误处理选项“失败时禁用位置”和“失败时挂起请求消息”不应都设置为 False，因为可能发生消息丢失。</span><span class="sxs-lookup"><span data-stu-id="2a90b-117">The error handling options "Disable location on failure" and "Suspend request message on failure" should not both be set to false since message loss may occur.</span></span> <span data-ttu-id="2a90b-118">请将一个或两个选项设置为 True。</span><span class="sxs-lookup"><span data-stu-id="2a90b-118">Please set one or both options to true</span></span> |

## <a name="explanation"></a><span data-ttu-id="2a90b-119">解释</span><span class="sxs-lookup"><span data-stu-id="2a90b-119">Explanation</span></span>  
 <span data-ttu-id="2a90b-120">在 Wcf-netmsmq 适配器中，选项**失败时禁用位置**并**在失败时挂起请求消息**不能同时应处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="2a90b-120">In the WCF-NetMsmq adapter, the options **Disable location on failure** and **Suspend request message on failure** should not both be selected.</span></span> <span data-ttu-id="2a90b-121">由于接收位置继续接收无效消息，但这些消息未被挂起并存储在 MessageBox 中，则可能发生消息丢失。</span><span class="sxs-lookup"><span data-stu-id="2a90b-121">Message loss may occur as the receive location continues to receive invalid messages, while these messages are not suspended and stored in the Message Box.</span></span>  

## <a name="user-action"></a><span data-ttu-id="2a90b-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="2a90b-122">User Action</span></span>  
 <span data-ttu-id="2a90b-123">使用以下过程配置适配器设置。</span><span class="sxs-lookup"><span data-stu-id="2a90b-123">Use the following procedure to configure adapter settings.</span></span>    

1. <span data-ttu-id="2a90b-124">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="2a90b-124">Open **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="2a90b-125">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="2a90b-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="2a90b-126">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="2a90b-126">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="2a90b-127">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="2a90b-127">Right-click the transport name.</span></span>  

5. <span data-ttu-id="2a90b-128">选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="2a90b-128">Select **Properties**.</span></span>  

6. <span data-ttu-id="2a90b-129">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="2a90b-129">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="2a90b-130">选择 **“配置”**。</span><span class="sxs-lookup"><span data-stu-id="2a90b-130">Select **Configure**.</span></span>  

8. <span data-ttu-id="2a90b-131">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，选择**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2a90b-131">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, select the **Messages** tab.</span></span>  

9. <span data-ttu-id="2a90b-132">在中**的错误处理**部分中，确保**失败时禁用位置**或**失败时挂起请求消息**检查。</span><span class="sxs-lookup"><span data-stu-id="2a90b-132">In the **Error Handling** section, ensure either **Disable location on failure** or **Suspend request message on failure** is checked.</span></span>
