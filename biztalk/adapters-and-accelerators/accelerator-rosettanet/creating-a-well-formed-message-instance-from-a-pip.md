---
title: 根据 PIP 创建格式正确的消息实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc0dc9610b171ffa2049c5a4951d3846451aa2db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284685"
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a><span data-ttu-id="ed1da-102">根据 PIP 创建格式正确的消息实例</span><span class="sxs-lookup"><span data-stu-id="ed1da-102">Creating a Well-Formed Message Instance from a PIP</span></span>
<span data-ttu-id="ed1da-103">本主题介绍如何生成格式正确的消息实例。</span><span class="sxs-lookup"><span data-stu-id="ed1da-103">This topic describes how to produce a well-formed message instance.</span></span> <span data-ttu-id="ed1da-104">从合作伙伴接口流程 (PIP) 都可以生成消息实例模板。</span><span class="sxs-lookup"><span data-stu-id="ed1da-104">You can generate a template for a message instance from the Partner Interface Process (PIP).</span></span> <span data-ttu-id="ed1da-105">完成后，必须修改该模板，以便它的格式正确，然后再添加你的数据。</span><span class="sxs-lookup"><span data-stu-id="ed1da-105">After doing this, you have to modify that template, so that it is well formed, before adding your data.</span></span>  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a><span data-ttu-id="ed1da-106">若要从 PIP 生成消息实例模板</span><span class="sxs-lookup"><span data-stu-id="ed1da-106">To generate a message instance template from the PIP</span></span>  
  
1. <span data-ttu-id="ed1da-107">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="ed1da-107">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2. <span data-ttu-id="ed1da-108">上**文件**菜单，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="ed1da-108">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="ed1da-109">找到\<*驱动器*\>\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNetSDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="ed1da-109">Locate \<*drive*\>\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNetSDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4. <span data-ttu-id="ed1da-110">在解决方案资源管理器，展开**Rnpip**，然后右键单击您要为其创建实例的 PIP。</span><span class="sxs-lookup"><span data-stu-id="ed1da-110">In Solution Explorer, expand **RNPIPs**, and then right-click the PIP for which you want to create an instance.</span></span>  
  
5. <span data-ttu-id="ed1da-111">单击**生成实例**。</span><span class="sxs-lookup"><span data-stu-id="ed1da-111">Click **Generate Instance**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ed1da-112">这将生成名为 pip"_output"追加到的文件名和扩展名为.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="ed1da-112">This generates a file named after the PIP, with "_output" appended to the file name, and with an .xml extension.</span></span> <span data-ttu-id="ed1da-113">输出窗格中的语句指示的位置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]生成的实例。</span><span class="sxs-lookup"><span data-stu-id="ed1da-113">A statement in the Output pane indicates where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] generated the instance.</span></span>  
  
### <a name="to-modify-the-message-instance-template"></a><span data-ttu-id="ed1da-114">若要修改消息实例模板</span><span class="sxs-lookup"><span data-stu-id="ed1da-114">To modify the message instance template</span></span>  
  
1. <span data-ttu-id="ed1da-115">在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，找到包含 XML 文件的文件夹并双击要打开的文件夹的文件名称。</span><span class="sxs-lookup"><span data-stu-id="ed1da-115">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, locate the folder holding the XML file, and double-click the file name to open the folder.</span></span>  
  
2. <span data-ttu-id="ed1da-116">添加之前，该值指示的 XML 并将编码版本的所有其他文本的 XML 头标记。</span><span class="sxs-lookup"><span data-stu-id="ed1da-116">Add an XML header tag before all other text indicating the version of XML and the encoding.</span></span> <span data-ttu-id="ed1da-117">例如：</span><span class="sxs-lookup"><span data-stu-id="ed1da-117">For example:</span></span>  
  
   ```  
   <?xml version="1.0" encoding="UTF-8" ?>  
   ```  
  
3. <span data-ttu-id="ed1da-118">刚添加的行之后, 添加指明 DTD 的 DOCTYPE 行。</span><span class="sxs-lookup"><span data-stu-id="ed1da-118">After the line that you just added, add a DOCTYPE line indicating the DTD.</span></span> <span data-ttu-id="ed1da-119">例如，对于 3A4 采购订单请求实例，行是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed1da-119">For example, for a 3A4 Purchase Order Request instance, the line would be as follows:</span></span>  
  
   ```  
   <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="ed1da-120">每个消息实例必须包含要处理的 DOCTYPE 行。</span><span class="sxs-lookup"><span data-stu-id="ed1da-120">Each message instance must include the DOCTYPE line to be processed.</span></span>  
  
4. <span data-ttu-id="ed1da-121">现在，您可以自定义此消息实例以满足你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="ed1da-121">You may now customize this message instance to suit your business needs.</span></span> <span data-ttu-id="ed1da-122">修改 XML 实例，使它不使用 XML 命名空间或命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="ed1da-122">Modify the XML instance so that it does not use XML namespaces or namespace prefixes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed1da-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed1da-123">See Also</span></span>  
 [<span data-ttu-id="ed1da-124">编程指南</span><span class="sxs-lookup"><span data-stu-id="ed1da-124">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)