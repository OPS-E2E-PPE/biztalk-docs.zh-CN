---
title: 创建 FRR 接收位置接收来自后端应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, creating
- creating, receive locations
- FRR, creating receive locations
ms.assetid: 78bd8084-ddec-4066-a474-ab5b1a0a849f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12e4e34ef888fa8c6ae7c91cc6b822c164daa9da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378379"
---
# <a name="creating-the-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="05c41-102">创建 FRR 接收位置接收来自后端应用程序</span><span class="sxs-lookup"><span data-stu-id="05c41-102">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>
<span data-ttu-id="05c41-103">若要执行 FIN 响应对帐，需要创建从后端应用程序接收消息的接收位置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="05c41-103">To perform FIN Response Reconciliation, you need to create a receive location that receives a message from the back-end application into [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span>  

 <span data-ttu-id="05c41-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="05c41-104">**Summary**</span></span>  

 <span data-ttu-id="05c41-105">创建接收位置具有以下属性和组件：</span><span class="sxs-lookup"><span data-stu-id="05c41-105">Create a receive location with the following properties and components:</span></span>  


| <span data-ttu-id="05c41-106">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="05c41-106">Property/Component</span></span> |                                                                 <span data-ttu-id="05c41-107">设置</span><span class="sxs-lookup"><span data-stu-id="05c41-107">Setting</span></span>                                                                 |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="05c41-108">接收端口</span><span class="sxs-lookup"><span data-stu-id="05c41-108">Receive port</span></span>    |                                                              <span data-ttu-id="05c41-109">单向端口</span><span class="sxs-lookup"><span data-stu-id="05c41-109">One-way port</span></span>                                                               |
|   <span data-ttu-id="05c41-110">传输类型</span><span class="sxs-lookup"><span data-stu-id="05c41-110">Transport type</span></span>   |                                           <span data-ttu-id="05c41-111">后端应用程序使用的传输类型</span><span class="sxs-lookup"><span data-stu-id="05c41-111">The transport type used by the back-end application</span></span>                                           |
|    <span data-ttu-id="05c41-112">地址 URI</span><span class="sxs-lookup"><span data-stu-id="05c41-112">Address URI</span></span>     |                                                   <span data-ttu-id="05c41-113">根据需要传输类型</span><span class="sxs-lookup"><span data-stu-id="05c41-113">As required for the transport type</span></span>                                                    |
|  <span data-ttu-id="05c41-114">接收处理程序</span><span class="sxs-lookup"><span data-stu-id="05c41-114">Receive handler</span></span>   |                                                        <span data-ttu-id="05c41-115">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="05c41-115">BizTalkServerApplication</span></span>                                                         |
|  <span data-ttu-id="05c41-116">接收管道</span><span class="sxs-lookup"><span data-stu-id="05c41-116">Receive pipeline</span></span>  | <span data-ttu-id="05c41-117">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收的 FRR 创建的管道</span><span class="sxs-lookup"><span data-stu-id="05c41-117">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR</span></span> |

### <a name="to-add-an-frr-receive-location-for-receiving-from-the-back-end-application"></a><span data-ttu-id="05c41-118">若要添加 FRR 接收位置以便接收来自后端应用程序</span><span class="sxs-lookup"><span data-stu-id="05c41-118">To add an FRR receive location for receiving from the back-end application</span></span>  

1. <span data-ttu-id="05c41-119">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1**节点。</span><span class="sxs-lookup"><span data-stu-id="05c41-119">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1** nodes.</span></span>  

2. <span data-ttu-id="05c41-120">右键单击**管道**，然后单击**刷新**。</span><span class="sxs-lookup"><span data-stu-id="05c41-120">Right-click **Pipelines**, and then click **Refresh**.</span></span>  

3. <span data-ttu-id="05c41-121">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="05c41-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

4. <span data-ttu-id="05c41-122">在接收端口属性对话框中，在**名称**框中，键入接收端口，例如 FRRBackEndReceivePort 的名称。</span><span class="sxs-lookup"><span data-stu-id="05c41-122">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port, such as FRRBackEndReceivePort.</span></span>  

5. <span data-ttu-id="05c41-123">单击**Apply**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="05c41-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  

6. <span data-ttu-id="05c41-124">在管理控制台中，右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="05c41-124">In the Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  

7. <span data-ttu-id="05c41-125">在选择接收端口对话框中，选择接收端口刚刚创建，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="05c41-125">In the Select a Receive Port dialog box, select the receive port that you just created, and then click **OK**.</span></span>  

8. <span data-ttu-id="05c41-126">在接收位置属性对话框中，在**名称**框中，键入接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="05c41-126">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  

9. <span data-ttu-id="05c41-127">在中**传输**部分中，对于**类型**文本框中，选择传输类型由后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="05c41-127">In the **Transport** section, for the **Type** text box, select the transport type used by the back-end application.</span></span>  

10. <span data-ttu-id="05c41-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="05c41-128">Click **Configure**.</span></span>  

11. <span data-ttu-id="05c41-129">在 FILE 传输属性对话框中，填写所需的传输类型的属性，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="05c41-129">In the FILE Transport Properties dialog box, fill in the properties required for the transport type, and then click **OK**.</span></span>  

12. <span data-ttu-id="05c41-130">在接收位置属性对话框中，对于**接收处理程序**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="05c41-130">In the Receive Location Properties dialog box, for **Receive Handler**, select **BizTalkServerApplication**.</span></span>  

13. <span data-ttu-id="05c41-131">在接收位置属性对话框中，对于**接收管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收的 FRR 创建的管道。</span><span class="sxs-lookup"><span data-stu-id="05c41-131">In the Receive Location Properties dialog box, for **Receive Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created for FRR.</span></span>  

14. <span data-ttu-id="05c41-132">单击**Apply**，然后单击**确定**以关闭**接收位置属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="05c41-132">Click **Apply**, and then click **OK** to close the **Receive Location Properties** dialog box.</span></span>  

15. <span data-ttu-id="05c41-133">在 BizTalk 浏览器中，右键单击您刚接收位置创建，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="05c41-133">In BizTalk Explorer, right-click the receive location that you just created, and then click **Enable**.</span></span>
