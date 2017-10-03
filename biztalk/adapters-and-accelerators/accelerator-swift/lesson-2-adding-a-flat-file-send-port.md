---
title: "第 2 课： 添加平面文件发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1370b4877c2e32055e2ee0a0aca1f922bd8668a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a><span data-ttu-id="75082-102">第 2 课： 添加平面文件发送端口</span><span class="sxs-lookup"><span data-stu-id="75082-102">Lesson 2: Adding a Flat File Send Port</span></span>
<span data-ttu-id="75082-103">在本课程中，你可以配置发送端口和发送位置。</span><span class="sxs-lookup"><span data-stu-id="75082-103">In this lesson, you configure the send port and the send location.</span></span> <span data-ttu-id="75082-104">发送端口用于定义要发送的消息的方式。</span><span class="sxs-lookup"><span data-stu-id="75082-104">You use the send port to define how you want messages sent.</span></span> <span data-ttu-id="75082-105">你还创建了发送的消息文件文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="75082-105">You also create a file folder location for sent messages.</span></span>  
  
### <a name="to-add-a-flat-file-send-port"></a><span data-ttu-id="75082-106">若要添加的平面文件，将发送端口</span><span class="sxs-lookup"><span data-stu-id="75082-106">To add a flat file send port</span></span>  
  
1.  <span data-ttu-id="75082-107">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="75082-107">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="75082-108">在发送端口属性对话框中，在**名称**框中，键入**MT103_FlatFile_SendPort**。</span><span class="sxs-lookup"><span data-stu-id="75082-108">In the Send Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_SendPort**.</span></span>  
  
3.  <span data-ttu-id="75082-109">在**传输**部分中，为**类型**框中，单击下拉列表中，，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="75082-109">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="75082-110">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="75082-110">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="75082-111">在文件传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="75082-111">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="75082-112">在浏览文件夹对话框中，移动到**\<驱动器 >: \Labs**文件夹，，然后单击**新建文件夹**。</span><span class="sxs-lookup"><span data-stu-id="75082-112">In the Browse For Folder dialog box, move to the **\<drive>:\Labs** folder, and then click **Make New Folder**.</span></span>  
  
7.  <span data-ttu-id="75082-113">创建**出站**文件夹中的**\<驱动器 >: \Labs**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="75082-113">Create an **Outbound** folder in **\<drive>:\Labs**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="75082-114">在**文件名**框中，键入**%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="75082-114">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="75082-115">在发送端口属性对话框中，单击的下拉列表**发送管道**框中，，然后选择**MT103SendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="75082-115">In the Send Port Properties dialog box, click the drop-down list for the **Send pipeline** box, and then select **MT103SendPipeline**.</span></span>  
  
10. <span data-ttu-id="75082-116">在左窗格中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="75082-116">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="75082-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="75082-117">Use this</span></span>|<span data-ttu-id="75082-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="75082-118">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="75082-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="75082-119">**Property**</span></span>|<span data-ttu-id="75082-120">选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="75082-120">Select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="75082-121">**运算符**</span><span class="sxs-lookup"><span data-stu-id="75082-121">**Operator**</span></span>|<span data-ttu-id="75082-122">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="75082-122">Select **==**.</span></span>|  
    |<span data-ttu-id="75082-123">**值**</span><span class="sxs-lookup"><span data-stu-id="75082-123">**Value**</span></span>|<span data-ttu-id="75082-124">类型**MT103_XML_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="75082-124">Type **MT103_XML_ReceivePort**.</span></span>|  
  
11. <span data-ttu-id="75082-125">单击**应用**，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="75082-125">Click **Apply**, and then click **OK.**</span></span>  
  
12. <span data-ttu-id="75082-126">在**发送端口**窗格中，右键单击**MT103_FlatFile_SendPort**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="75082-126">In the **Send Ports** pane, right-click **MT103_FlatFile_SendPort**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="75082-127">继续执行[模块 5： 添加平面文件位置和 XML 发送端口接收](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="75082-127">Proceed to [Module 5: Adding a Flat File Receive Location and XML Send Port](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span></span>