---
title: 第 1 课： 添加 XML 接收端口和位置 |Microsoft Docs
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
ms.assetid: 252bc080-3820-44cc-8749-715869f3f684
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a6f5665fe460084319401e24090a8e92ea8987
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010230"
---
# <a name="lesson-1-adding-xml-receive-port-and-location"></a><span data-ttu-id="ea64c-102">第 1 课： 添加 XML 接收端口和位置</span><span class="sxs-lookup"><span data-stu-id="ea64c-102">Lesson 1: Adding XML Receive Port and Location</span></span>
<span data-ttu-id="ea64c-103">接收端口是相似接收位置的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="ea64c-103">A receive port is a logical grouping of similar receive locations.</span></span> <span data-ttu-id="ea64c-104">接收位置传入的消息和用于处理该消息的管道定义特定地址 （例如 URL 或文件的位置）。</span><span class="sxs-lookup"><span data-stu-id="ea64c-104">A receive location defines a specific address (such as a URL or file location) for an incoming message and the pipeline that is used to process the message.</span></span>  
  
### <a name="to-add-a-receive-port"></a><span data-ttu-id="ea64c-105">若要添加接收端口</span><span class="sxs-lookup"><span data-stu-id="ea64c-105">To add a receive port</span></span>  
  
1. <span data-ttu-id="ea64c-106">启动**BizTalk Server 管理**控制台。</span><span class="sxs-lookup"><span data-stu-id="ea64c-106">Start **BizTalk Server Administration** console.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ea64c-107">在 BizTalk Server 管理控制台也可以打开从 Visual Studio 中通过单击**BizTalk Server 管理**中**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="ea64c-107">The BizTalk Server Administration Console can also be opened from within Visual Studio by clicking **BizTalk Server Administration** in the **Tools** menu.</span></span>  
  
2. <span data-ttu-id="ea64c-108">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**节点，然后**BizTalk 组**节点，则**应用程序**节点，然后**BizTalk Application 1**节点。</span><span class="sxs-lookup"><span data-stu-id="ea64c-108">In the BizTalk Server Administration Console, expand the **BizTalk Server Administration** node, then the **BizTalk Group** node, then the **Applications** node, and then the **BizTalk Application 1** node.</span></span>  
  
3. <span data-ttu-id="ea64c-109">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-109">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4. <span data-ttu-id="ea64c-110">在接收端口属性对话框中，在**名称**框中，键入**MT103_XML_ReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-110">In the Receive Port Properties dialog box, in the **Name** box, type **MT103_XML_ReceivePort**.</span></span>  
  
5. <span data-ttu-id="ea64c-111">单击**Apply**以绑定端口，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="ea64c-111">Click **Apply** to bind the port, and then click **OK.**</span></span>  
  
6. <span data-ttu-id="ea64c-112">右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-112">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7. <span data-ttu-id="ea64c-113">在选择接收端口对话框中，单击**MT103_XML_ReceivePort**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-113">In the Select a Receive Port dialog box, click **MT103_XML_ReceivePort**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="ea64c-114">在接收位置属性对话框中，在**名称**框中，键入**MT103_XML_ReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-114">In the Receive Location Properties dialog box, in the **Name** box, type **MT103_XML_ReceiveLocation**.</span></span>  
  
9. <span data-ttu-id="ea64c-115">在中**传输**部分中，对于**类型**文本框中，单击下拉列表，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-115">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="ea64c-116">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="ea64c-116">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="ea64c-117">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-117">In the FILE Transport Properties dialog box, click **Browse**.</span></span> <span data-ttu-id="ea64c-118">将移动到**\<驱动器\>: \Labs**文件夹，，然后单击**建立新文件夹**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-118">Move to the **\<drive\>:\Labs** folder, and then click **Make New Folder**.</span></span>  
  
12. <span data-ttu-id="ea64c-119">在浏览文件夹对话框中，创建**入站**中的文件夹**\<驱动器\>: \Labs**，然后创建**XMLFile**中文件夹**\<驱动器\>: \Labs\Inbound**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-119">In the Browse For Folder dialog box, create an **Inbound** folder in **\<drive\>:\Labs**, and then create an **XMLFile** folder in **\<drive\>:\Labs\Inbound**.</span></span> <span data-ttu-id="ea64c-120">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="ea64c-120">Click **OK**.</span></span>  
  
13. <span data-ttu-id="ea64c-121">在 FILE 传输属性对话框中，确保 **\*.xml**中输入**文件掩码**框中，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-121">In the FILE Transport Properties dialog box, ensure that **\*.xml** is entered in the **File Mask** box, and then click **OK**.</span></span>  
  
14. <span data-ttu-id="ea64c-122">在接收位置属性对话框中，确保**BizTalkServerApplication**为输入**接收处理程序**框。</span><span class="sxs-lookup"><span data-stu-id="ea64c-122">In the Receive Location Properties dialog box, ensure that **BizTalkServerApplication** is entered for the **Receive handler** box.</span></span>  
  
15. <span data-ttu-id="ea64c-123">有关**接收管道**框中，选择**XMLReceive**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ea64c-123">For the **Receive Pipeline** box, select **XMLReceive** from the drop-down list.</span></span>  
  
16. <span data-ttu-id="ea64c-124">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-124">Click **Apply**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="ea64c-125">在 BizTalk Server 管理控制台中，单击**接收位置**，右键单击**MT103_XML_ReceiveLocation**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="ea64c-125">In the BizTalk Server Administration Console, click **Receive Locations**, right-click **MT103_XML_ReceiveLocation**, and then click **Enable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea64c-126">启用接收位置后，BizTalk 将主动轮询文件文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea64c-126">After you enable the receive location, BizTalk actively polls your file folder.</span></span>  
  
    <span data-ttu-id="ea64c-127">请继续执行[第 2 课： 添加平面文件发送端口](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="ea64c-127">Proceed to [Lesson 2: Adding the Flat File Send Port](../../adapters-and-accelerators/accelerator-swift/lesson-2-adding-a-flat-file-send-port.md).</span></span>