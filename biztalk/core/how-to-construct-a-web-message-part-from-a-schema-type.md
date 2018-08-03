---
title: 如何构造 Web 消息部分从架构类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, schema types
- Web messages, creating
- Transform shape [Orchestration Designer]
- Web messages, Transform shape [Orchestration Designer]
ms.assetid: 4452ade6-b10f-4564-bffc-18114896aeeb
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be8fd01e67309387749e7e512eca84bdb0f83db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984790"
---
# <a name="how-to-construct-a-web-message-part-from-a-schema-type"></a><span data-ttu-id="ede94-102">如何从架构类型构造 Web 消息部分</span><span class="sxs-lookup"><span data-stu-id="ede94-102">How to Construct a Web Message Part from a Schema Type</span></span>
<span data-ttu-id="ede94-103">从架构类型中使用创建 Web 消息部分**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="ede94-103">You create a Web message part from a schema type by using a **Transform** shape.</span></span> <span data-ttu-id="ede94-104">也可以通过使用 .NET 帮助程序类设置各个部分来从架构类型创建 Web 消息部分。</span><span class="sxs-lookup"><span data-stu-id="ede94-104">Alternatively, you can create a Web message part from a schema type by using a .NET helper class to set the parts.</span></span> <span data-ttu-id="ede94-105">使用.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="ede94-105">For more information on creating message types by using a .NET class, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
### <a name="to-construct-a-web-message-part-from-a-schema-type"></a><span data-ttu-id="ede94-106">从架构类型构建 Web 消息部分</span><span class="sxs-lookup"><span data-stu-id="ede94-106">To construct a Web message part from a schema type</span></span>  
  
1. <span data-ttu-id="ede94-107">添加一个新映射。</span><span class="sxs-lookup"><span data-stu-id="ede94-107">Add a new map.</span></span> <span data-ttu-id="ede94-108">有关创建映射的信息，请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="ede94-108">For information about creating maps, see [How to Create New Maps](../core/how-to-create-new-maps.md).</span></span>  
  
2. <span data-ttu-id="ede94-109">在 BizTalk 映射器中，单击**打开目标架构**中**目标架构**窗格的映射，并在**BizTalk 类型选取器**对话框中，展开**架构**节点中，选择添加的 Web 引用的架构，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ede94-109">In BizTalk Mapper, click **Open Destination Schema** in the **Destination Schema** pane of the map and in the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the schema for the added Web reference, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ede94-110">Web 引用架构的格式**\<项目默认命名空间\>。\<Web 引用名\>。引用**。</span><span class="sxs-lookup"><span data-stu-id="ede94-110">The format of the Web reference schema is **\<project default namespace\>.\<Web reference name\>.Reference**.</span></span>  
  
3. <span data-ttu-id="ede94-111">在中**目标架构的根节点**对话框中，选择目标架构的根节点，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ede94-111">In the **Root Node for Target Schema** dialog box, select a root node for the destination schema, and then click **OK**.</span></span> <span data-ttu-id="ede94-112">有关如何确定 Web 消息部分类型的根节点的详细信息，请参阅[如何确定 Web 消息部分类型](../core/how-to-determine-a-web-message-part-type.md)。</span><span class="sxs-lookup"><span data-stu-id="ede94-112">For more information about how to determine a root node for a Web message part type, see [How to Determine a Web Message Part Type](../core/how-to-determine-a-web-message-part-type.md).</span></span>  
  
4. <span data-ttu-id="ede94-113">单击**打开源架构**中**源架构**窗格的映射，并在**BizTalk 类型选取器**对话框中，展开**架构**节点中，选择要将数据从，映射的源架构，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ede94-113">Click **Open Source Schema** in the **Source Schema** pane of the map and in the **BizTalk Type Picker** dialog box, expand the **Schemas** node, select the source schema to map data from, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="ede94-114">在 BizTalk 映射器中，创建源架构和目标架构之间的链接。</span><span class="sxs-lookup"><span data-stu-id="ede94-114">In the BizTalk Mapper, create links between the source schema and target schema.</span></span>  
  
6. <span data-ttu-id="ede94-115">打开现有的业务流程 （或创建新的业务流程），打开**工具箱**，然后单击**BizTalk 业务流程**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ede94-115">Open an existing orchestration (or create a new orchestration), open the **Toolbox**, and click the **BizTalk Orchestrations** tab.</span></span>  
  
7. <span data-ttu-id="ede94-116">拖动**构造消息**向业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="ede94-116">Drag a **Construct Message** shape to the orchestration.</span></span>  
  
8. <span data-ttu-id="ede94-117">编辑**构造的消息**yo 为创建 Web 消息类型的属性以包含消息实例。</span><span class="sxs-lookup"><span data-stu-id="ede94-117">Edit the **Message Constructed** property to include the message instance that yo created for the Web message type.</span></span>  
  
9. <span data-ttu-id="ede94-118">拖动**转换**形状拖至**构造消息**形状，然后双击以打开**转换配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="ede94-118">Drag a **Transform** shape onto the **Construct Message** shape and double-click to open the **Transform Configuration** dialog box.</span></span>  
  
10. <span data-ttu-id="ede94-119">单击**现有的映射**按钮，然后选择在步骤 1 中创建的映射**完全限定的映射名称**列表框。</span><span class="sxs-lookup"><span data-stu-id="ede94-119">Click the **Existing Map** button and select the map that you created in step one in the **Fully Qualified Map Name** list box.</span></span>  
  
11. <span data-ttu-id="ede94-120">在中**转换**窗格中，选择**源**。</span><span class="sxs-lookup"><span data-stu-id="ede94-120">In the **Transform** pane, select **Source**.</span></span> <span data-ttu-id="ede94-121">在中**源转换**窗格中，选择一个有效的消息实例从列表框。</span><span class="sxs-lookup"><span data-stu-id="ede94-121">In the **Source Transform** pane, select a valid message instance from the list box.</span></span>  
  
12. <span data-ttu-id="ede94-122">在中**转换**窗格中，选择**目标**。</span><span class="sxs-lookup"><span data-stu-id="ede94-122">In the **Transform** pane, select **Destination**.</span></span> <span data-ttu-id="ede94-123">在中**目标转换**窗格中，选择 Web 消息实例从列表框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ede94-123">In the **Destination Transform** pane, select the Web message instance from the list box, and then click **OK**.</span></span>  
  
    <span data-ttu-id="ede94-124">有关使用详细信息**转换配置**对话框中，请参阅[如何配置转换形状](../core/how-to-configure-the-transform-shape.md)。</span><span class="sxs-lookup"><span data-stu-id="ede94-124">For more information about using the **Transform Configuration** dialog box, see [How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md).</span></span>  
  
    <span data-ttu-id="ede94-125">您也可以使用此过程将 Web 方法响应消息实例映射到其他 Web 消息实例。</span><span class="sxs-lookup"><span data-stu-id="ede94-125">You can also use this procedure to map the Web method response message instance to another Web message instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede94-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ede94-126">See Also</span></span>  
 [<span data-ttu-id="ede94-127">构造 Web 消息</span><span class="sxs-lookup"><span data-stu-id="ede94-127">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)