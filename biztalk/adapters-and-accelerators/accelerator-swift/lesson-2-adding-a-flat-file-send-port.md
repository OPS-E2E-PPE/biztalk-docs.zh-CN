---
title: 第 2 课：添加平面文件发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, flat files
- flat files, send ports
- creating, send ports
- send ports, creating
ms.assetid: 33dceb0d-85f5-4e19-820f-cd33b60cd32a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc7a9be734f2b4f360dd006492a9c9298bd0658b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377492"
---
# <a name="lesson-2-adding-a-flat-file-send-port"></a><span data-ttu-id="4a913-102">第 2 课：添加平面文件发送端口</span><span class="sxs-lookup"><span data-stu-id="4a913-102">Lesson 2: Adding a Flat File Send Port</span></span>
<span data-ttu-id="4a913-103">在本课程中，你可以配置发送端口和发送位置。</span><span class="sxs-lookup"><span data-stu-id="4a913-103">In this lesson, you configure the send port and the send location.</span></span> <span data-ttu-id="4a913-104">使用发送端口以定义要发送的消息的方式。</span><span class="sxs-lookup"><span data-stu-id="4a913-104">You use the send port to define how you want messages sent.</span></span> <span data-ttu-id="4a913-105">您还创建了发送的消息文件文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="4a913-105">You also create a file folder location for sent messages.</span></span>  

### <a name="to-add-a-flat-file-send-port"></a><span data-ttu-id="4a913-106">若要添加平面文件发送端口</span><span class="sxs-lookup"><span data-stu-id="4a913-106">To add a flat file send port</span></span>  

1. <span data-ttu-id="4a913-107">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="4a913-107">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="4a913-108">在发送端口属性对话框中，在**名称**框中，键入**MT103_FlatFile_SendPort**。</span><span class="sxs-lookup"><span data-stu-id="4a913-108">In the Send Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_SendPort**.</span></span>  

3. <span data-ttu-id="4a913-109">在中**传输**部分中，对于**类型**框中，单击下拉列表中，并选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="4a913-109">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  

4. <span data-ttu-id="4a913-110">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="4a913-110">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

5. <span data-ttu-id="4a913-111">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="4a913-111">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6. <span data-ttu-id="4a913-112">在浏览文件夹对话框中，转至**\<驱动器\>: \Labs**文件夹，，然后单击**建立新文件夹**。</span><span class="sxs-lookup"><span data-stu-id="4a913-112">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs** folder, and then click **Make New Folder**.</span></span>  

7. <span data-ttu-id="4a913-113">创建**出站**中的文件夹**\<驱动器\>: \Labs**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4a913-113">Create an **Outbound** folder in **\<drive\>:\Labs**, and then click **OK**.</span></span>  

8. <span data-ttu-id="4a913-114">在中**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4a913-114">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  

9. <span data-ttu-id="4a913-115">在发送端口属性对话框中，单击的下拉列表**发送管道**框，并选择**MT103SendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="4a913-115">In the Send Port Properties dialog box, click the drop-down list for the **Send pipeline** box, and then select **MT103SendPipeline**.</span></span>  

10. <span data-ttu-id="4a913-116">在左窗格中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4a913-116">In the left pane, click **Filters**, and then do the following:</span></span>  


    |   <span data-ttu-id="4a913-117">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4a913-117">Use this</span></span>   |           <span data-ttu-id="4a913-118">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4a913-118">To do this</span></span>            |
    |--------------|---------------------------------|
    | <span data-ttu-id="4a913-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="4a913-119">**Property**</span></span> | <span data-ttu-id="4a913-120">选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="4a913-120">Select **BTS.ReceivePortName**.</span></span> |
    | <span data-ttu-id="4a913-121">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="4a913-121">**Operator**</span></span> |         <span data-ttu-id="4a913-122">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="4a913-122">Select **==**.</span></span>          |
    |  <span data-ttu-id="4a913-123">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="4a913-123">**Value**</span></span>   | <span data-ttu-id="4a913-124">类型**MT103_XML_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="4a913-124">Type **MT103_XML_ReceivePort**.</span></span> |


11. <span data-ttu-id="4a913-125">单击**Apply**，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="4a913-125">Click **Apply**, and then click **OK.**</span></span>  

12. <span data-ttu-id="4a913-126">在中**发送端口**窗格中，右键单击**MT103_FlatFile_SendPort**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="4a913-126">In the **Send Ports** pane, right-click **MT103_FlatFile_SendPort**, and then click **Start**.</span></span>  

    <span data-ttu-id="4a913-127">请继续执行[模块 5:添加平面文件接收位置和 XML 发送端口](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="4a913-127">Proceed to [Module 5: Adding a Flat File Receive Location and XML Send Port](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md).</span></span>