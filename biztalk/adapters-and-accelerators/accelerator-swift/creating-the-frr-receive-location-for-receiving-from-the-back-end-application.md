---
title: "创建 FRR 接收位置用于接收从后端应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46895ff64e6585c8b80979c09874dffb510cf049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="28cf4-102">创建 FRR 接收位置用于接收从后端应用程序</span><span class="sxs-lookup"><span data-stu-id="28cf4-102">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>
<span data-ttu-id="28cf4-103">若要执行 FIN 响应对帐，你需要创建一个从后端应用程序置于接收消息的接收位置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="28cf4-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the back-end application into [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  
  
 <span data-ttu-id="28cf4-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="28cf4-104">**Summary**</span></span>  
  
 <span data-ttu-id="28cf4-105">创建具有以下属性和组件接收位置：</span><span class="sxs-lookup"><span data-stu-id="28cf4-105">Create a receive location with the following properties and components:</span></span>  
  
|<span data-ttu-id="28cf4-106">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="28cf4-106">Property/Component</span></span>|<span data-ttu-id="28cf4-107">设置</span><span class="sxs-lookup"><span data-stu-id="28cf4-107">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="28cf4-108">接收端口</span><span class="sxs-lookup"><span data-stu-id="28cf4-108">Receive port</span></span>|<span data-ttu-id="28cf4-109">单向端口</span><span class="sxs-lookup"><span data-stu-id="28cf4-109">One-way port</span></span>|  
|<span data-ttu-id="28cf4-110">传输类型</span><span class="sxs-lookup"><span data-stu-id="28cf4-110">Transport type</span></span>|<span data-ttu-id="28cf4-111">后端应用程序使用的传输类型</span><span class="sxs-lookup"><span data-stu-id="28cf4-111">The transport type used by the back-end application</span></span>|  
|<span data-ttu-id="28cf4-112">地址 URI</span><span class="sxs-lookup"><span data-stu-id="28cf4-112">Address URI</span></span>|<span data-ttu-id="28cf4-113">所必需的传输类型</span><span class="sxs-lookup"><span data-stu-id="28cf4-113">As required for the transport type</span></span>|  
|<span data-ttu-id="28cf4-114">接收处理程序</span><span class="sxs-lookup"><span data-stu-id="28cf4-114">Receive handler</span></span>|<span data-ttu-id="28cf4-115">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="28cf4-115">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="28cf4-116">接收管道</span><span class="sxs-lookup"><span data-stu-id="28cf4-116">Receive pipeline</span></span>|<span data-ttu-id="28cf4-117">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收为 FRR 创建的管道</span><span class="sxs-lookup"><span data-stu-id="28cf4-117">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR</span></span>|  
  
### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="28cf4-118">若要添加 FRR 接收位置用于接收从后端应用程序</span><span class="sxs-lookup"><span data-stu-id="28cf4-118">To add an FRR receive location for receiving from the back-end application</span></span>  
  
1.  <span data-ttu-id="28cf4-119">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**节点。</span><span class="sxs-lookup"><span data-stu-id="28cf4-119">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span>  
  
2.  <span data-ttu-id="28cf4-120">右键单击**管道**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-120">Right-click **Pipelines**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="28cf4-121">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="28cf4-122">在接收端口属性对话框中，在**名称**框中，键入接收端口，如 FRRBackEndReceivePort 的名称。</span><span class="sxs-lookup"><span data-stu-id="28cf4-122">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRBackEndReceivePort.</span></span>  
  
5.  <span data-ttu-id="28cf4-123">单击**应用**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="28cf4-124">在管理控制台中，右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-124">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="28cf4-125">在选择接收端口对话框中，选择你刚接收端口创建，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-125">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="28cf4-126">在接收位置属性对话框中，在**名称**框中，键入接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="28cf4-126">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  
  
9. <span data-ttu-id="28cf4-127">在**传输**部分中，为**类型**文本框中，选择后端应用程序使用的传输类型。</span><span class="sxs-lookup"><span data-stu-id="28cf4-127">In the **Transport** section, for the **Type** text box, select the transport type used by the back-end application.</span></span>  
  
10. <span data-ttu-id="28cf4-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-128">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="28cf4-129">在文件传输属性对话框中，填写所需的传输类型的属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-129">In the FILE Transport Properties dialog box, fill in the properties required for the transport type, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="28cf4-130">在接收位置属性对话框中，为**接收处理程序**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-130">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  
  
13. <span data-ttu-id="28cf4-131">在接收位置属性对话框中，为**接收管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收为 FRR 创建的管道。</span><span class="sxs-lookup"><span data-stu-id="28cf4-131">In the Receive Location Properties dialog box, for **Receive Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR.</span></span>  
  
14. <span data-ttu-id="28cf4-132">单击**应用**，然后单击**确定**关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="28cf4-132">Click **Apply**, and then click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
15. <span data-ttu-id="28cf4-133">在 BizTalk 资源管理器，右键单击你刚接收位置创建，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="28cf4-133">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>