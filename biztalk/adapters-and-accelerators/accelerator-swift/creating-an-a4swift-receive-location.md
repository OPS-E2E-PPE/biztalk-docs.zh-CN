---
title: 创建 A4SWIFT 接收位置 |Microsoft Docs
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
ms.assetid: 712cf42f-8d71-47e9-b2bf-3da158b74fe4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b19330a4d4ab207c7d5e0f920dadb432b733df19
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968366"
---
# <a name="creating-an-a4swift-receive-location"></a><span data-ttu-id="910fd-102">创建 A4SWIFT 接收位置</span><span class="sxs-lookup"><span data-stu-id="910fd-102">Creating an A4SWIFT Receive Location</span></span>
<span data-ttu-id="910fd-103">必须创建[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收位置，以便能够从 SWIFT 通过网络接收到消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]下, 图中所示。</span><span class="sxs-lookup"><span data-stu-id="910fd-103">You must create an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive location to enable message reception from the SWIFT network by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], as shown in the following figure.</span></span> <span data-ttu-id="910fd-104">接收位置接收来自入站的文件文件夹的平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="910fd-104">The receive location receives flat file messages from an inbound file folder.</span></span>  

 <span data-ttu-id="910fd-105">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")</span><span class="sxs-lookup"><span data-stu-id="910fd-105">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-receive-location-configuration.gif "A4SWIFT_Receive_Location_Configuration")</span></span>  

 <span data-ttu-id="910fd-106">**摘要**</span><span class="sxs-lookup"><span data-stu-id="910fd-106">**Summary**</span></span>  

 <span data-ttu-id="910fd-107">创建并绑定的单向接收端口，然后创建并启用接收位置使用以下属性和组件：</span><span class="sxs-lookup"><span data-stu-id="910fd-107">Create and bind a one-way receive port, and then create and enable a receive location with the following properties and components:</span></span>  


| <span data-ttu-id="910fd-108">属性/组件</span><span class="sxs-lookup"><span data-stu-id="910fd-108">Property/Components</span></span> |                                                             <span data-ttu-id="910fd-109">设置</span><span class="sxs-lookup"><span data-stu-id="910fd-109">Setting</span></span>                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="910fd-110">接收端口</span><span class="sxs-lookup"><span data-stu-id="910fd-110">Receive port</span></span>     |                                                          <span data-ttu-id="910fd-111">单向端口</span><span class="sxs-lookup"><span data-stu-id="910fd-111">One-way port</span></span>                                                           |
|   <span data-ttu-id="910fd-112">传输类型</span><span class="sxs-lookup"><span data-stu-id="910fd-112">Transport type</span></span>    |                                                              <span data-ttu-id="910fd-113">FILE</span><span class="sxs-lookup"><span data-stu-id="910fd-113">FILE</span></span>                                                               |
|     <span data-ttu-id="910fd-114">地址 URI</span><span class="sxs-lookup"><span data-stu-id="910fd-114">Address URI</span></span>     |                                     <span data-ttu-id="910fd-115">你想要接收消息的文件夹的名称</span><span class="sxs-lookup"><span data-stu-id="910fd-115">Name of the folder that you want to receive the message</span></span>                                     |
|      <span data-ttu-id="910fd-116">文件掩码</span><span class="sxs-lookup"><span data-stu-id="910fd-116">File mask</span></span>      |                  <span data-ttu-id="910fd-117">\*.*\<扩展\>*，其中\<*扩展*\>是传入的扩展平面文件消息</span><span class="sxs-lookup"><span data-stu-id="910fd-117">\*.*\<extension\>*, where \<*extension*\> is the extension of the incoming flat file message</span></span>                   |
|   <span data-ttu-id="910fd-118">接收处理程序</span><span class="sxs-lookup"><span data-stu-id="910fd-118">Receive handler</span></span>   |                                                    <span data-ttu-id="910fd-119">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="910fd-119">BizTalkServerApplication</span></span>                                                     |
|  <span data-ttu-id="910fd-120">接收管道</span><span class="sxs-lookup"><span data-stu-id="910fd-120">Receive pipeline</span></span>   | <span data-ttu-id="910fd-121">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]接收你创建的管道</span><span class="sxs-lookup"><span data-stu-id="910fd-121">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receive pipeline that you created</span></span> |

### <a name="to-add-the-receive-port-and-location"></a><span data-ttu-id="910fd-122">若要添加接收端口和位置</span><span class="sxs-lookup"><span data-stu-id="910fd-122">To add the receive port and location</span></span>  

1.  <span data-ttu-id="910fd-123">启动**BizTalk Server 管理**控制台。</span><span class="sxs-lookup"><span data-stu-id="910fd-123">Start **BizTalk Server Administration** console.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="910fd-124">在 BizTalk Server 管理控制台也可以打开从 Visual Studio 中通过单击**BizTalk Server 管理**中**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="910fd-124">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  

2.  <span data-ttu-id="910fd-125">在管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="910fd-125">In Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  

3.  <span data-ttu-id="910fd-126">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="910fd-126">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  

4.  <span data-ttu-id="910fd-127">在接收端口属性对话框中，在**名称**框中，键入接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="910fd-127">In the Receive Port Properties dialog box, in the **Name** box, type a name for the receive port.</span></span>  

5.  <span data-ttu-id="910fd-128">单击**Apply**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="910fd-128">Click **Apply** to bind the port, and then click **OK**.</span></span>  

6.  <span data-ttu-id="910fd-129">右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="910fd-129">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  

7.  <span data-ttu-id="910fd-130">在选择接收端口对话框框中，单击接收端口刚刚创建，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="910fd-130">In the Select a Receive Port dialog box, click the receive port that you just created, and then click **OK**.</span></span>  

8.  <span data-ttu-id="910fd-131">在接收位置属性对话框中，在**名称**框中，键入接收位置的名称。</span><span class="sxs-lookup"><span data-stu-id="910fd-131">In the Receive Location Properties dialog box, in the **Name** box, type a name for the receive location.</span></span>  

9. <span data-ttu-id="910fd-132">在中**传输**部分中，对于**类型**文本框中，单击下拉列表，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="910fd-132">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  

10. <span data-ttu-id="910fd-133">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="910fd-133">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

11. <span data-ttu-id="910fd-134">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="910fd-134">In the FILE Transport Properties dialog box, click **Browse**.</span></span> <span data-ttu-id="910fd-135">转到的文件夹，你想要接收的消息。</span><span class="sxs-lookup"><span data-stu-id="910fd-135">Move to the folder that you want to receive the message.</span></span> <span data-ttu-id="910fd-136">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="910fd-136">Click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="910fd-137">如果此文件夹不存在，则可以创建使用其**建立新文件夹**命令。</span><span class="sxs-lookup"><span data-stu-id="910fd-137">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  

12. <span data-ttu-id="910fd-138">在 FILE 传输属性对话框中，在**文件掩码**框中，输入 **\*。\<*扩展*\>**，其中\<*扩展*\>是传入的扩展平面文件消息，例如 **.txt**。</span><span class="sxs-lookup"><span data-stu-id="910fd-138">In the FILE Transport Properties dialog box, in the **File Mask** box, enter **\*.\<*extension*\>**, where \<*extension*\> is the extension of the incoming flat file message, such as **.txt**.</span></span> <span data-ttu-id="910fd-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="910fd-139">Click **OK**.</span></span>  

13. <span data-ttu-id="910fd-140">在接收位置属性对话框中，确保**BizTalkServerApplication**为输入**接收处理程序**框。</span><span class="sxs-lookup"><span data-stu-id="910fd-140">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  

14. <span data-ttu-id="910fd-141">有关**接收管道**框中，从下拉列表中选择自定义接收管道。</span><span class="sxs-lookup"><span data-stu-id="910fd-141">For the **Receive Pipeline** box, select your custom receive pipeline from the drop-down list.</span></span>  

15. <span data-ttu-id="910fd-142">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="910fd-142">Click **Apply**, and then click **OK**.</span></span>  

16. <span data-ttu-id="910fd-143">在 BizTalk Server 管理控制台中，单击**接收位置**，右键单击您刚接收位置创建，并单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="910fd-143">In the BizTalk Server Administration Console, click **Receive Locations**, right-click the receive location that you just created, and then click **Enable**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="910fd-144">启用接收位置后，BizTalk 将主动轮询文件文件夹。</span><span class="sxs-lookup"><span data-stu-id="910fd-144">After you enable the receive location, BizTalk actively polls your file folder.</span></span>