---
title: "在一个 SAP 用于 BizTalk 中的 SAP 适配器创建 RFC 概述 |Microsoft 文档"
description: "创建 RFC，RFC 目标和发送 RFC 从 SAP 系统-BizTalk 适配器包 (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35937183-fc1e-49cd-8a75-8f62effe0013
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802a2e33b8bc902dc784276ce7c1d9c3f37f3b12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-and-send-an-rfc-in-sap"></a><span data-ttu-id="460f4-103">创建和 SAP 中发送 RFC</span><span class="sxs-lookup"><span data-stu-id="460f4-103">Create and send an RFC in SAP</span></span>
<span data-ttu-id="460f4-104">列出在该 SAP 系统创建 RFC 上完成的高级任务。</span><span class="sxs-lookup"><span data-stu-id="460f4-104">Lists high-level tasks to complete on the SAP system to create an RFC.</span></span> <span data-ttu-id="460f4-105">每个任务可能涉及到非常详细的过程。</span><span class="sxs-lookup"><span data-stu-id="460f4-105">Each task may involve very detailed procedures.</span></span> <span data-ttu-id="460f4-106">因此，我们建议联系您的 SAP 管理员来完成这些任务，或指 SAP 指南。</span><span class="sxs-lookup"><span data-stu-id="460f4-106">As a result, we recommend contacting your SAP administrator to complete these tasks, or refer to the SAP guidance.</span></span>  
  
## <a name="create-an-rfc"></a><span data-ttu-id="460f4-107">创建 RFC</span><span class="sxs-lookup"><span data-stu-id="460f4-107">Create an RFC</span></span>  
  
1.  <span data-ttu-id="460f4-108">启动 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="460f4-108">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="460f4-109">转到事务 SE37 （函数生成器） 中，输入 RFC 名称，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="460f4-109">Go to Transaction SE37 (Function Builder), enter the RFC name, and click **Create**.</span></span>  
  
3.  <span data-ttu-id="460f4-110">输入现有函数组在其下将创建 RFC，RFC，有关的简短说明，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="460f4-110">Enter an existing function group under which the RFC will be created, a short description for the RFC, and click **Save**.</span></span>  
  
4.  <span data-ttu-id="460f4-111">在**属性**选项卡上，选择**Remote-Enabled 模块**单选按钮。</span><span class="sxs-lookup"><span data-stu-id="460f4-111">In the **Attributes** tab, select the **Remote-Enabled Module** radio button.</span></span>  
  
5.  <span data-ttu-id="460f4-112">在**导入**选项卡上，输入导入参数。</span><span class="sxs-lookup"><span data-stu-id="460f4-112">In the **Import** tab, enter the import parameters.</span></span> <span data-ttu-id="460f4-113">这些参数用于将外部数据传递给函数模块。</span><span class="sxs-lookup"><span data-stu-id="460f4-113">These parameters are used for passing the external data to the function module.</span></span>  
  
6.  <span data-ttu-id="460f4-114">在**导出**选项卡上，输入导出参数。</span><span class="sxs-lookup"><span data-stu-id="460f4-114">In the **Export** tab, enter the export parameters.</span></span>  
  
7.  <span data-ttu-id="460f4-115">在**Changing**选项卡上，输入不断变化的参数。</span><span class="sxs-lookup"><span data-stu-id="460f4-115">In the **Changing** tab, enter the changing parameters.</span></span>  
  
8.  <span data-ttu-id="460f4-116">在**表**选项卡上，输入表名称。</span><span class="sxs-lookup"><span data-stu-id="460f4-116">In the **Tables** tab, enter the table names.</span></span>  
  
9. <span data-ttu-id="460f4-117">在**异常**选项卡上，输入来处理错误的异常。</span><span class="sxs-lookup"><span data-stu-id="460f4-117">In the **Exceptions** tab, enter the exceptions to handle errors.</span></span>  
  
10. <span data-ttu-id="460f4-118">在**源代码**选项卡上，输入 RFC 源代码 （逻辑）。</span><span class="sxs-lookup"><span data-stu-id="460f4-118">In the **Source Code** tab, enter the source code (logic) for the RFC.</span></span>  
  
11. <span data-ttu-id="460f4-119">单击**激活**工具栏激活函数模块上的图标。</span><span class="sxs-lookup"><span data-stu-id="460f4-119">Click the **Activate** icon on the toolbar to activate the function module.</span></span>  

## <a name="create-an-rfc-destination"></a><span data-ttu-id="460f4-120">创建一个 RFC 目标</span><span class="sxs-lookup"><span data-stu-id="460f4-120">Create an RFC destination</span></span>  
  
1.  <span data-ttu-id="460f4-121">启动 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="460f4-121">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="460f4-122">转到事务 SM59 （显示和维护 RFC 目标）。</span><span class="sxs-lookup"><span data-stu-id="460f4-122">Go to Transaction SM59 (Display and Maintain RFC Destinations).</span></span>  
  
3.  <span data-ttu-id="460f4-123">从菜单栏中，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="460f4-123">From the menu bar, click **Create**.</span></span>  
  
4.  <span data-ttu-id="460f4-124">输入 RFC 目标、 连接类型、 说明，，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="460f4-124">Enter the RFC destination, connection type, description, and then press Enter.</span></span>  
  
5.  <span data-ttu-id="460f4-125">选择**注册服务器程序**单选按钮输入程序 ID、 网关主机和网关服务。</span><span class="sxs-lookup"><span data-stu-id="460f4-125">Select the **Registered Server Program** radio-button, enter the program ID, gateway host, and gateway service.</span></span>  
  
6.  <span data-ttu-id="460f4-126">保存 RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="460f4-126">Save the RFC destination.</span></span>  

## <a name="send-an-rfc-from-an-sap-system"></a><span data-ttu-id="460f4-127">从 SAP 系统发送 RFC</span><span class="sxs-lookup"><span data-stu-id="460f4-127">Send an RFC from an SAP system</span></span>  
  
1.  <span data-ttu-id="460f4-128">启动 SAP GUI。</span><span class="sxs-lookup"><span data-stu-id="460f4-128">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="460f4-129">创建使用 BD54 事务的逻辑系统。</span><span class="sxs-lookup"><span data-stu-id="460f4-129">Create a logical system using BD54 transaction.</span></span>  
  
3.  <span data-ttu-id="460f4-130">创建一个 RFC 目标中使用 SM59 事务的 TCP/IP 连接。</span><span class="sxs-lookup"><span data-stu-id="460f4-130">Create an RFC destination in TCP/IP connections using SM59 transaction.</span></span>  
  
4.  <span data-ttu-id="460f4-131">创建使用 WE21 事务的端口，并将其附加到的最后一步中创建的 RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="460f4-131">Create a port using WE21 transaction and attach it to the RFC destination created in the last step.</span></span>  
  
5.  <span data-ttu-id="460f4-132">通过使用 SE37 触发 RFC。</span><span class="sxs-lookup"><span data-stu-id="460f4-132">Trigger an RFC by using SE37.</span></span> <span data-ttu-id="460f4-133">此 RFC 必须包含逻辑以便进行 RFC 调用外部应用程序，然后从该应用程序收到的响应。</span><span class="sxs-lookup"><span data-stu-id="460f4-133">This RFC must contain the logic to make an RFC call to an external application and then receive a response from that application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460f4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="460f4-134">See Also</span></span>  
 [<span data-ttu-id="460f4-135">对于特定 SAP 适配器方案中使用 SAP GUI 执行任务</span><span class="sxs-lookup"><span data-stu-id="460f4-135">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)