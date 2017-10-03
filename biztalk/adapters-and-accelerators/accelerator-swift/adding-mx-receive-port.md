---
title: "添加 MX 接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4818d6af-df1d-481e-becf-1af633735248
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69123b876bdda4b5f999277a1710cdeb1cb61fe7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-mx-receive-port"></a><span data-ttu-id="40465-102">添加 MX 接收端口</span><span class="sxs-lookup"><span data-stu-id="40465-102">Adding MX Receive Port</span></span>
<span data-ttu-id="40465-103">**若要添加 MX 接收端口：**</span><span class="sxs-lookup"><span data-stu-id="40465-103">**To add an MX receive port:**</span></span>  
  
1.  <span data-ttu-id="40465-104">启动**BizTalk Server 管理**控制台。</span><span class="sxs-lookup"><span data-stu-id="40465-104">Start **BizTalk Server Administration** console.</span></span>  
  
2.  <span data-ttu-id="40465-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="40465-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="40465-106">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="40465-106">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="40465-107">在名称框中，接收端口属性对话框中键入**MX_ 接收端口**。</span><span class="sxs-lookup"><span data-stu-id="40465-107">In the Receive Port Properties dialog box, in the Name box, type **MX_ Receive Port**.</span></span>  
  
5.  <span data-ttu-id="40465-108">单击**应用**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="40465-108">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="40465-109">右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="40465-109">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="40465-110">在选择接收端口对话框中，单击**MX_ 接收端口**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="40465-110">In the Select a Receive Port dialog box, click **MX_ Receive Port**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="40465-111">在名称框中，接收位置属性对话框中键入**MX_ 接收位置**。</span><span class="sxs-lookup"><span data-stu-id="40465-111">In the Receive Location Properties dialog box, in the Name box, type **MX_ Receive Location**.</span></span>  
  
9. <span data-ttu-id="40465-112">在传输部分中，在类型文本框中，单击下拉列表中，，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="40465-112">In the Transport section, for the Type text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="40465-113">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="40465-113">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="40465-114">在文件传输属性对话框中，单击**浏览**，然后选择文件位置。</span><span class="sxs-lookup"><span data-stu-id="40465-114">In the FILE Transport Properties dialog box, click **Browse**, and then select a file location.</span></span>  
  
12. <span data-ttu-id="40465-115">在文件传输属性对话框中，确保\*.xml 在文件掩码框中，输入，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="40465-115">In the FILE Transport Properties dialog box, ensure that \*.xml is entered in the File Mask box, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="40465-116">在接收位置属性对话框中，确保为接收处理程序框中输入时 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="40465-116">In the Receive Location Properties dialog box, ensure that BizTalkServerApplication is entered for the Receive handler box.</span></span>  
  
14. <span data-ttu-id="40465-117">在接收管道中，选择**接收管道**（管道项目中部署了接收管道） 从下拉列表中，单击**应用**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="40465-117">In the Receive Pipeline box, select **Receive Pipeline** (the receive pipeline that has been deployed in the Pipeline project) from the drop-down list, click **Apply**, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="40465-118">右键单击您刚配置，，然后单击的位置**启用**。</span><span class="sxs-lookup"><span data-stu-id="40465-118">Right-click the location you have just configured, and then click **Enable**.</span></span>