---
title: "从 PIP 创建格式正确的消息实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e16020afb17d17c8add8e973ade0cd0c5cfcbbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a><span data-ttu-id="cf47f-102">从 PIP 创建格式正确的消息实例</span><span class="sxs-lookup"><span data-stu-id="cf47f-102">Creating a Well-Formed Message Instance from a PIP</span></span>
<span data-ttu-id="cf47f-103">本主题介绍如何生成格式正确的消息实例。</span><span class="sxs-lookup"><span data-stu-id="cf47f-103">This topic describes how to produce a well-formed message instance.</span></span> <span data-ttu-id="cf47f-104">你可以根据合作伙伴接口流程 (PIP) 为消息实例生成模板。</span><span class="sxs-lookup"><span data-stu-id="cf47f-104">You can generate a template for a message instance from the Partner Interface Process (PIP).</span></span> <span data-ttu-id="cf47f-105">执行此操作后，必须先修改该模板，以确保该模板的格式正确，然后才能添加数据。</span><span class="sxs-lookup"><span data-stu-id="cf47f-105">After doing this, you have to modify that template, so that it is well formed, before adding your data.</span></span>  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a><span data-ttu-id="cf47f-106">根据 PIP 生成消息实例模板</span><span class="sxs-lookup"><span data-stu-id="cf47f-106">To generate a message instance template from the PIP</span></span>  
  
1.  <span data-ttu-id="cf47f-107">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="cf47f-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="cf47f-108">上**文件**菜单上，指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="cf47f-108">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="cf47f-109">找到\<*驱动器*> files\microsoft BizTalk\<版本 > Accelerator for RosettaNetSDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="cf47f-109">Locate \<*drive*>\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNetSDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="cf47f-110">在解决方案资源管理器，展开**RNPIPs**，然后右键单击你想要创建实例 PIP。</span><span class="sxs-lookup"><span data-stu-id="cf47f-110">In Solution Explorer, expand **RNPIPs**, and then right-click the PIP for which you want to create an instance.</span></span>  
  
5.  <span data-ttu-id="cf47f-111">单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="cf47f-111">Click **Generate Instance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf47f-112">这将生成一个根据 PIP 命名的文件，该文件名附加“_output”，并具有扩展名 .xml。</span><span class="sxs-lookup"><span data-stu-id="cf47f-112">This generates a file named after the PIP, with "_output" appended to the file name, and with an .xml extension.</span></span> <span data-ttu-id="cf47f-113">“输出”窗格中的语句指明 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 生成的实例的位置。</span><span class="sxs-lookup"><span data-stu-id="cf47f-113">A statement in the Output pane indicates where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] generated the instance.</span></span>  
  
### <a name="to-modify-the-message-instance-template"></a><span data-ttu-id="cf47f-114">修改消息实例模板</span><span class="sxs-lookup"><span data-stu-id="cf47f-114">To modify the message instance template</span></span>  
  
1.  <span data-ttu-id="cf47f-115">在 [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 资源管理器中，找到包含该 XML 文件的文件夹，然后双击文件名打开该文件夹。</span><span class="sxs-lookup"><span data-stu-id="cf47f-115">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, locate the folder holding the XML file, and double-click the file name to open the folder.</span></span>  
  
2.  <span data-ttu-id="cf47f-116">在所有其他文本前添加指示 XML 版本和编码的 XML 头标记。</span><span class="sxs-lookup"><span data-stu-id="cf47f-116">Add an XML header tag before all other text indicating the version of XML and the encoding.</span></span> <span data-ttu-id="cf47f-117">例如：</span><span class="sxs-lookup"><span data-stu-id="cf47f-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" ?>  
    ```  
  
3.  <span data-ttu-id="cf47f-118">在刚添加的行后面，添加指明 DTD 的 DOCTYPE 行。</span><span class="sxs-lookup"><span data-stu-id="cf47f-118">After the line that you just added, add a DOCTYPE line indicating the DTD.</span></span> <span data-ttu-id="cf47f-119">例如，对于“3A4 采购订单请求”实例，该行如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf47f-119">For example, for a 3A4 Purchase Order Request instance, the line would be as follows:</span></span>  
  
    ```  
    <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cf47f-120">每个消息实例都必须包括要进行处理的 DOCTYPE 行。</span><span class="sxs-lookup"><span data-stu-id="cf47f-120">Each message instance must include the DOCTYPE line to be processed.</span></span>  
  
4.  <span data-ttu-id="cf47f-121">现在可自定义此消息实例以满足你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="cf47f-121">You may now customize this message instance to suit your business needs.</span></span> <span data-ttu-id="cf47f-122">修改 XML 实例，不在其中使用 XML 命名空间或命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="cf47f-122">Modify the XML instance so that it does not use XML namespaces or namespace prefixes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf47f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf47f-123">See Also</span></span>  
 [<span data-ttu-id="cf47f-124">编程指南</span><span class="sxs-lookup"><span data-stu-id="cf47f-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)