---
title: 第 1 课： 添加平面文件接收端口和位置 |Microsoft Docs
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
- receive ports, creating
- creating, receive ports
ms.assetid: 881f58d8-f541-4a85-b534-cb1ca627c002
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e23525715be1816684ffa680f99cf8f8bd88ceca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966262"
---
# <a name="lesson-1-adding-flat-file-receive-port-and-location"></a><span data-ttu-id="f4b41-102">第 1 课： 添加平面文件接收端口和位置</span><span class="sxs-lookup"><span data-stu-id="f4b41-102">Lesson 1: Adding Flat File Receive Port and Location</span></span>
<span data-ttu-id="f4b41-103">接收端口始终具有添加接收端口时，必须配置一个关联的接收位置。</span><span class="sxs-lookup"><span data-stu-id="f4b41-103">The receive port always has an associated receive location that you must configure when you add the receive port.</span></span> <span data-ttu-id="f4b41-104">接收位置定义传入消息的管道和管道，用于处理该消息的特定地址。</span><span class="sxs-lookup"><span data-stu-id="f4b41-104">A receive location defines a specific address for an incoming message and the pipeline that you use to process the message.</span></span>  
  
### <a name="to-add-a-receive-port"></a><span data-ttu-id="f4b41-105">若要添加接收端口</span><span class="sxs-lookup"><span data-stu-id="f4b41-105">To add a receive port</span></span>  
  
1. <span data-ttu-id="f4b41-106">在 BizTalk Server 管理控制台中，右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-106">In the BizTalk Server Administration Console, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="f4b41-107">在接收端口属性对话框中，在**名称**框中，键入**MT103_FlatFile_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-107">In the Receive Port Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceivePort**.</span></span>  
  
3. <span data-ttu-id="f4b41-108">单击**Apply**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-108">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="f4b41-109">在 BizTalk Server 管理控制台中，右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-109">In the BizTalk Server Administration Console, right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
5. <span data-ttu-id="f4b41-110">在选择接收端口对话框中，单击**MT103_FlatFile_ReceivePort**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-110">In the Select a Receive Port dialog box, click **MT103_FlatFile_ReceivePort**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="f4b41-111">在接收位置属性对话框中，在**名称**框中，键入**MT103_FlatFile_ReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-111">In the Receive Location Properties dialog box, in the **Name** box, type **MT103_FlatFile_ReceiveLocation**.</span></span>  
  
7. <span data-ttu-id="f4b41-112">在中**传输**部分中，对于**类型**文本框中，单击下拉列表，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-112">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
8. <span data-ttu-id="f4b41-113">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="f4b41-113">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
9. <span data-ttu-id="f4b41-114">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-114">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
10. <span data-ttu-id="f4b41-115">在浏览文件夹对话框中，转至**\<驱动器\>: \Labs\Inbound**文件夹，，然后单击**建立新文件夹**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-115">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs\Inbound** folder, and then click **Make New Folder**.</span></span>  
  
11. <span data-ttu-id="f4b41-116">创建**FlatFile**中的文件夹**\<驱动器\>: \Labs\Inbound**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-116">Create a **FlatFile** folder in **\<drive\>:\Labs\Inbound**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="f4b41-117">在中**文件掩码**框中，键入 **\*.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-117">In the **File mask** box, type **\*.txt**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="f4b41-118">在接收位置属性对话框中，确保**BizTalkServerApplication**为输入**接收处理程序**框。</span><span class="sxs-lookup"><span data-stu-id="f4b41-118">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
14. <span data-ttu-id="f4b41-119">有关**接收管道**框中，选择**MT103ReceivePipeline**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f4b41-119">For the **Receive Pipeline** box, select **MT103ReceivePipeline** from the drop-down list.</span></span>  
  
15. <span data-ttu-id="f4b41-120">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-120">Click **Apply**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="f4b41-121">在 BizTalk Server 管理控制台中，单击**接收位置**，右键单击**MT103_FlatFile_ReceiveLocation**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="f4b41-121">In the BizTalk Server Administration Console, click **Receive Locations**, right-click **MT103_FlatFile_ReceiveLocation**, and then click **Enable**.</span></span>  
  
    <span data-ttu-id="f4b41-122">请继续执行[第 2 课： 添加 XML 发送端口](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b41-122">Proceed to [Lesson 2: Adding an XML Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-an-xml-send-port.md).</span></span>